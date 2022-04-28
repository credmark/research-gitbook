# LPing Return of Uniswap Pools

## Executive Summary <a href="#docs-internal-guid-becf5aa2-7fff-246f-1f36-cc8009afdf4c" id="docs-internal-guid-becf5aa2-7fff-246f-1f36-cc8009afdf4c"></a>

Liquidity Providers (LP) have always suffered from finding out the real-time annual percentage rate (APR) they get in return for providing liquidity in an Uniswap Pool. This became more complicated with the launch of Uniswap V3 and mostly with their concept of concentrated liquidity.

This document lists and explains the method to calculate the real-time APR of a position in liquidity pools on Uniswap V2 and Uniswap V3, even factoring in Impermanent Loss and Gas Fees.

APR is calculated in dollar value, i.e., how much return a user is getting in dollars compared to the amount of initial capital in dollars.

A sample code is also attached to help readers implement the method explained below.

## Uniswap V2 APR

In Uniswap V2, there is a fixed 0.3% fee on all trades.

Upon providing liquidity, users are issued(minted) LP Tokens of the pool, proportional to the share of their capital in the liquidity pool.

Fees are added to the pool and accrue in real time. Since LP tokens are awarded to liquidity providers in proportion to their capital in the pool and fees for all the traders are added to the pool itself, users can claim the fee (with the capital) by redeeming their LP tokens.

To measure the APR for liquidity provided in any Uniswap V2 liquidity pool, we have to go through these steps.

### Step 1

First, we have to determine the ratio of the user's LP tokens to the total supply of that particular LP token.

**User’s LP token ratio** = User’s LP token balance /  total supply of the LP token



### Step 2

Then we have to multiply that ratio by the total balance of each token present in the pool to get the cumulative token balance (initial capital + fees) of the user.

**Total Present Capital** = User’s LP token ratio \* total liquidity in the pool



### Step 3

After that, we will calculate the fees accrued by providing liquidity as

**Fees accrued** = (Total Present Capital - Total Initial Capital) \* Dollar value\


### Step 4

Also, we will have to factor impermanent loss on the capital

**IL** = Difference in dollar value of initial capital from the starting of liquidity position to the current time

### Step 5

And gas fees associated with the transaction(minting LP tokens)

**Gas fees cost** = Gas units \* Gas price \* dollar value of ETH (at transaction time)

### Step 6

Then, Absolute profit and loss is calculated as,

**PnL**= Fees accrued - IL - Gas fees cost

### Step 7

The final step to APR Calculation

**APR** = PnL / Initial\_capital \* (age of the position / year time)



## Uniswap V3 APR

The process to calculate APR for a position in Uniswap V3 is completely different as compared to Uniswap V2.

The ability to set custom price ranges in which to provide liquidity is the main difference between Uniswap V3 and Uniswap V2. This results in a dynamic distribution of liquidity that changes every time LPs mint or burn positions or when a price changes, so we must calculate the share of active liquidity that this position had at each swap in order to calculate accrued fees for a position (defined as a price range (pa,pb) and total liquidity provided).&#x20;



NOTE: All the code for the Uniswap V3 APR Engine can be found at:

[https://github.com/credmark/credmark-risk-and-research/tree/main/research-development/APREngine](https://github.com/credmark/credmark-risk-and-research/tree/main/research-development/APREngine)

(This is currently a private repository link, please reach to us on our Discord if you need access)

For calculating the APR for liquidity position in Uniswap V3, we have to assume that each tick range is a pool like Uniswap V2 with its own liquidity distribution

### Step 1

First step is to download all the swaps of the pools for a given timeframe using a subgraph.

![](https://lh5.googleusercontent.com/OE34T-\_c1iPxGaEqDr\_v6DVvD7UN4sjXwsoPq8IBtTpoT6x8-4DFnBlHUmPvjHN7OYZWdu-cdSgy0kxewAsoG5uXaihz-O8Kas94NwWArSBMqwL8hsuRobFGmxjpq9Gjr5VfCaz8)



To get the most accurate results, use a web3 client to query an archive node or the Uniswap v3 Oracle and fetch the historical active liquidity in every block, but I used the maximum granularity available in The Graph right now to speed calculations and make it public (hourly data). When testing with hourly data and simple positions, a few cross-checks with revert. finance data show a precision of around +/-5 percent (without rebalancing).



### Step 2

Next step is to fetch the liquidity data for the pool with same time frame

It will be used to merge swap and liquidity data to keep track of active liquidity during the swap

![](https://lh4.googleusercontent.com/Ei5XmxnNZXDQw584--vigYCVrIvZhmNbmjLXgVZE6bf1vcxqntahq-QzhNa-hegZjfprI7MsvL0qP3UAqwUljxqfW0SwqztXt5YGEzzJpgMm7ODtZb-hrFJsyqyQwVkHoLur0qle)



### Step 3

The next step is to merge swaps and liquidity data to determine what the active liquidity was at the time of the swap.&#x20;

For this example, we'll assume that the liquidity remains constant for the entire hour.

&#x20; &#x20;

![](https://lh3.googleusercontent.com/hkflhgvVK5Y6M3oIUX8W8LKEFpxWAv1AT962dmJpC2-AX-i7AI46Sil1hjApJ91Tj6tM7NM9ihZa1mxHsJr5zvlKJJQ48QgRcd\_ApdwhmK441TxMLUzVrATgpO3cS5zzM\_7M5DiJ)



### Step 4

Next step is to create a position that will be simulated. The combination of (liquidity, tick lower, tick upper) defines a position

Liquidity is calculated using the ‘liquidity for amounts’ formula and the following parameters: an initial capital amount ($), the price at the mint, and the range of the position (tick\_lower, tick\_upper). Until an additional add or burn is performed, liquidity will remain constant.

&#x20; &#x20;

![](https://lh5.googleusercontent.com/8t79znQzJQNjP4Wy4Qs1psd0TDMUOGTW5DA8hYC2NNOT3pk6\_BlcRksbqgMq8aTmpZfTKWl-hE81BjrXWJXetsrDMXCvrKMMhT8dFoI2glInAzGPNBU1ABsdnISBNN1JwH93seaW)



### Step 5

Now we move onto calculating absolute PnL for the position.&#x20;

For every swap executed in the backtested pool, we calculate the fees accrued by the position and the actual impermanent loss (IL) of the position.(just like we did for the whole pool in case of Uniswap V2)

### Step 6

We will calculate the fees accrued by providing liquidity (for each swap during the active position) as

**Fees accrued** = Swap\_amountIn \* fee\_tier \* (position\_liquidity/active\_liquidity)

![](https://lh3.googleusercontent.com/bjffja3OCzeVKRC4Nw3mD-A-ZRKEiXePyBIitkjbwlARqa5jgGBLZxJJ4bgLL6XDVE31ljGfqBNxTXkrljwSPjnNzducfDnUB22D-e26ENXVTjTAz8OxtwfhJcahP41YZBphHj-N)

### Step 7

Also, Impermanent loss will be calculated in the same way(for each swap of the active position)

**IL** = Difference in dollar value of initial capital from the starting of liquidity position to the current time

&#x20;      &#x20;

![](https://lh6.googleusercontent.com/UwjHlLij5W3yapxcLjXv5Sg0QDzBZBUZ6yjisgXk3eHjEtnFfmXoYJgIXvYd834UKSXC1wKS3eRWTS0Iuy9pDrcktzvsBFv5xrtxUOJ-pC\_\_mJFniIzlPqHni8Y3dVJ71Q3Ww2t7)

### Step 8

And gas fees associated with the transaction(minting LP tokens)

**Gas fees cost** = Gas\_units \* gas\_price



### Step 9

Then, Absolute profit and loss is calculated as,

**PnL**= Accumulated Fees accrued - Accumulated IL - Gas fees cost



### Step 10

The final step to APR Calculation

**APR** = PnL / Initial\_capital \* (age of the position / year time)



![](https://lh6.googleusercontent.com/LDrN-iTQFwbTM1Bof1cCBQoaKJpxpg9FshFCD4j27yvSVWRvIfKk7Mr\_MjvhpkipVa-44Y7EOwGYAtDXeowKEYD7e8yDzH71pd7-HvEJIz4KFzytx0VF4chR59jJBbqrRDeGj3HG)

### &#x20; Contributors

| **Discord Handle** | **ETH Address**                                              | **Reward**                          | **Contribution** |
| ------------------ | ------------------------------------------------------------ | ----------------------------------- | ---------------- |
| airboom#0400       | <p>0x84eAF08c13E86cD1603Bb8de7f5F61Fa115771bc</p><p><br></p> | <p>0 $CMK (internal)</p><p><br></p> | Original version |

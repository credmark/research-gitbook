# Total Value Locked (TVL)

## What is TVL?

Total value locked (TVL) is the overall value of crypto assets deposited in a decentralized finance (Defi) protocol \[1]. The meaning is the same across different platforms but the way it is calculated is different. Like, for Uniswap being a DEX, the TVL would be the number of fees collected by the platform. For AAVE being a borrow and lending platform, TVL would be the number of assets deposited by the users plus the liquidity in each asset.

## How is TVL calculated?

As the definition states, TVL is the overall crypto assets value, usually in USD ($). To calculate the value, we need the amount of each asset and their USD value.&#x20;

Let’s suppose there is a&#x20;

* Platform P,&#x20;
* Assets A = {A1, A2, … , An }&#x20;
* USD values V = {V1, V2, … , Vn}.&#x20;
* Q(a), a function that returns quantity or the number of tokens of the required asset.

**TVL = ( Σ Q ( A\[i] ) \* V\[i] ) for i = { 1, 2, …, n}**



Example -&#x20;

\
_Suppose Credy have a money jar with $ 1000 and 10 ETH in it at a point of time. So we can say that Credy has $1000 and 10 ETH as the total value locked. After a while, his friend asked him for the help of $500 and 2 ETH as he wanted to provide liquidity to a pool. So, he unlocked his jar and lent him the money, and locked it again. After this, he had a total value locked of $500 and 8 ETH._

_Since TVL is calculated in $ and assuming 1 ETH = $3000, we can say his TVL dropped from $ 31000 to $24500 after helping out his friend._

## TVL Modelling

A detailed analysis for the Data modeling can be found [here](../../data/modeling/tvl-methodology.md).

## References:

1. Coindesk, https://www.coindesk.com/learn/why-tvl-matters-in-defi-total-value-locked-explained/

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 $CMK (internal) | Original version |

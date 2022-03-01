# 🚀 On-chain Gas fees (ETH)

### Gas Fees

Gas fees is the reward given to miners for putting transactions in the blockchain or executing them. You can think of it as the tip you give to your waiter at the end of the meal.

As blockchains are decentralized in nature, the transactions are added and validated in the network blockchain by anonymous miners or validators.

There are two ways miners can earn Ethereum tokens. The first is by mining Ethereum to get paid in newly minted Ethereum tokens. The second is getting Ethereum as fees from users by processing their transactions.

### How is gas fees calculated?

There are two components of gas fees-

1. Gas units(gas)
2. Gas price per unit(gasPrice)

### Gas

Gas refers to the unit that measures the amount of computational effort required to execute specific operations on the Ethereum network.

[Ethereum’ yellow paper](https://ethereum.github.io/yellowpaper/paper.pdf) has specifications on how many units of work a transaction has. For example, if your transaction is to simply add two numbers, that is 3 units of work. If it is multiplication, that would be 5 units of work and so on. This unit of work is called gas.

Since each Ethereum transaction requires computational resources to execute, each transaction requires a fee. Gas refers to the fee required to conduct a transaction on Ethereum successfully.

### Gas Price

Gas price is the cost per unit of gas that the user is willing to pay. Gas prices are denoted in gwei, which itself is a denomination of ETH - each gwei is equal to 0.000000001 ETH (10^-9 ETH).

Gas price alone does not actually determine how much we have to pay for a particular transaction. To calculate the transaction fee, we have to multiply the gas used by the transaction fee, which is measured in gwei.

### Gas Limit

It is very difficult to know exactly how much gas your transaction will take. As a developer of a smart contract or a user of the network, you don't want to blindly execute a transaction and realize your transaction took hundreds of dollars worth of Ether. To avoid this situation, you can specify a gas limit which indicates the maximum amount of gas you are willing to buy to execute your transaction.

### Transaction Fee

Transaction fee is calculated as - **(Gas Limit \* Gas Price)**

Gas fees are paid in Ethereum's native currency, ether (ETH).&#x20;

For example, If your transaction takes 100000 gas and you set the gas price to 40 Gwei, you end up paying 4000000 Gwei for your transaction, which is 0.004 ETH.

**\*While the amount of gas required for any given transaction remains constant, the gas price is dynamic.\***

### Block Gas Limit

There is a restriction on the size of each Ethereum block. Unlike Bitcoin where the block size is restricted by its size in bytes, Ethereum blocks are restricted by the sum of the transaction gas used in the block.

If the block gas limit was 10,000,000, then each block (blocks are mined roughly every 15 seconds) could include a maximum of 476 transactions assuming each transaction used 21,000 gas. Of course in reality each transaction will use a different amount of gas.

### Effect of London Hardfork

The London Upgrade was implemented on August 5th, 2021, to make transacting on Ethereum more predictable for users by overhauling Ethereum's transaction-fee-mechanism.

Starting with the London network upgrade, every block has a base fee, the minimum price per unit of gas for inclusion in this block, calculated by the network based on demand for block space. As the base fee of the transaction fee is burnt, users are also expected to set a tip (priority fee) in their transactions. The tip compensates miners for executing and propagating user transactions in blocks and is expected to be set automatically by most wallets.

Calculating the total transaction fee works as follows: **Gas units (limit) \* (Base fee + Tip)**

Let's say Alice has to pay Bob 1 ETH. In the transaction, the gx limit is 21,000 units and the base fee is 100 gwei. Jordan includes a tip of 10 gwei.

Using the formula above we can calculate this as 21,000 \* (100 + 10) = 2,310,000 gwei or 0.00231 ETH.

### Why can Gas Fees get so high?

There are a number of reasons for the gas fees to get so high occasionally.

1. **Increasing gas units (complexity of transaction)**

Performing any operation on Ethereum requires consuming gas, and gas space is limited per block. Fees include calculations, storing or manipulating data, or transferring tokens, consuming different amounts of "gas" units. As dapp functionality grows more complex, the number of operations a smart contract performs also grows, meaning each transaction takes up more space of a limited size block and will require more gas units to be executed.

2\. **Increasing gas price**

More than three thousand decentralized applications (also known as dApps) are running on the Ethereum blockchain, all of which are looking to have their transactions included alongside other Ethereum network users. This puts the miners in a situation where they must choose a certain number of transactions to validate. All transactions cannot be validated simultaneously, as the energy cost for miners would be exceedingly high.

All the unprocessed transactions are stored in something known as ‘mempool’, a combination of memory and pool. Here miners can decide which transaction they want to validate.

This population and congestion of the network further increases the gas price. If there's too much demand, users must offer a higher tip amount to try and outbid other users' transactions. A higher tip can make it more likely that your transaction will get into the next block.

3**. Increasing price of Ether**

Gas fees are calculated and paid in Ethereum's native currency, ether (ETH) and if the price of Ether increases, so does the FIAT value of the transaction fee.

For example, If we were to execute a same transaction which requires a transaction fee of 0.001 ETH, assuming gas price is constant, in two different point of time, one during the beginning of network when the price of ETH was $1 and other now, where the price of ETH is $3000, although the transaction fee remain same (0.001 ETH), the dollar value of the transaction fee has increased over 3000 times.

### Ethereum network average gas price chart

The following chart shows the variation of Gas Price of ethereum network from its inception in 2016 to until now.

![Ethereum Historical Gas Price](https://lh3.googleusercontent.com/m23\_\_Aw9azbogOcUsqrrVJ6yDw72WMzFH1r83wv6MYlkjmM5mTdS77-Bw1cIaMeQt-7zC8zPX\_vxAFUxIjC9EY4kAqbQnj1oZaKUGS8yEwgRAlKQPlHsUfOTVpJw0WBRXJsKflgF)

The peaks in this chart are reference to exorbitantly high gas prices within the ethereum network. These peaks are in correlation with the popularity and congestion of the network due to new market trends such as decentralized games and NFTs.

### Ether Price Chart

The following chart shows the variation of Ether price from its inception in 2016 to until now.

![Ether Price Chart](https://lh5.googleusercontent.com/H7Qqn7i3bscH71tL6mi6F0IsN7W24KRt6dAcVo\_VkEHUbXsMPF5yHSZG-RWqfPII-aYK\_0Epj0y2shzAvm-8MLuTBGEVUYGoYkXbqZu4FZNHlcVrSFE90j97oS8zFz0NYORfEP75)

The price of ETH has been on constant rise since its inception in 2016 increasing dollar value of gas fees to over 5300 times as price went from $0.75 to $4000.

### Gas Fee Categorization

Gas fees are often categorized into three types while making a transaction-

1. Low
2. Average
3. High
4. Instant

These classifications differ only in the amount of Priority fees included with the transaction to incentivize miners to include the transaction in the block quickly.

While different wallets have different approaches to calculate the priority fees for low, medium and high gas fees transactions, the most popular values are mentioned below.

* Low - 0 Gwei per unit
* Medium - 10 Gwei per unit
* High - 20 Gwei per unit
* Instant - 30 Gwei per Unit

These values are added on top of the base fee (which varies as per the complexity of transaction)as tips to miners.

### Method to fetch current gas fees data

We will be using the [Etherscan’s API](https://docs.etherscan.io/api-endpoints/gas-tracker) to request last used gas Prices.

```
# PYthon Code
etherscanGasOracle= ‘https://api.etherscan.io/api?module=gastracker&action=gasoracle&apikey={0}’.format(ETHERSCAN_API_KEY)’
 resJs = requests.get(etherscanGasOracle).json()[‘result’]
 # type(resJs)
 print(resJs)
```

**Output**

```
"LastBlock":"13053741",
"SafeGasPrice":"20",
"ProposeGasPrice":"22",
"FastGasPrice":"24",
"suggestBaseFee":"19.230609716",
"gasUsedRatio":"0.370119078777807,0.8954731,0.550911766666667,0.212457033333333,0.552463633333333"
```

**SafeGasPrice, ProposeGasPrice, FastGasPrice**: Different Gas prices used to incentivize miners to quickly include transaction in the next block

**suggestBaseFee**: the baseFee of the next pending block

**gasUsedRatio**: gas used ratio of last 4 blocks to estimate how busy the network is.

### **Method to fetch historic gas fees data**

We will be using [OwlOracle’s](https://owlracle.info/eth) API to fetch historic gas fees data.

```
def fetch_gasFees_data(timeframe=1440, candles='100', page='1'):
    OwlOraceleURL = 'https://owlracle.info/eth/history?timeframe={0}&candles={1}&page={2}'.format(timeframe, candles, page)
    resJs = requests.get(OwlOraceleURL).json()
    # type(resJs)
    return resJs

gasFeesdata = list()

# Looping through the first 100 pages to get transaction fees data

 for i in range(1,101):
        data = fetch_gasFees_data(page=i)
        gasFeesdata.extend(data)
        
        if i % 10 == 0 :
            time.sleep(60)
        i += 1
```

**Data Sample:**

****

| timestamp                | open   | close  | low   | high   | avgGas      |
| ------------------------ | ------ | ------ | ----- | ------ | ----------- |
| 2022-02-21T13:40:03.438Z | 51     | 42.09  | 38.11 | 90.15  | 87906.26041 |
| 2022-02-21T11:59:41.592Z | 66.21  | 51     | 26    | 138.38 | 92530.43248 |
| 2022-02-21T03:03:02.247Z | 64.21  | 65.1   | 36.5  | 865    | 98052.89461 |
| 2022-02-20T23:59:27.810Z | 89.69  | 72.47  | 29.27 | 188.03 | 90658.77843 |
| 2022-02-20T16:59:19.832Z | 48.13  | 92.07  | 26.48 | 1750   | 86077.74295 |
| 2022-02-20T07:59:08.258Z | 73.78  | 54.29  | 26.07 | 291.2  | 64999.10071 |
| 2022-02-19T23:59:47.502Z | 63.94  | 67.98  | 32.78 | 129.39 | 90331.62364 |
| 2022-02-19T21:59:22.684Z | 45.97  | 58.91  | 34.73 | 5555   | 92180.52222 |
| 2022-02-19T12:59:47.503Z | 59.35  | 49.24  | 27.5  | 90     | 89091.39733 |
| 2022-02-19T04:31:07.716Z | 52.13  | 50.4   | 36.43 | 130.35 | 89579.28608 |
| 2022-02-18T23:59:42.754Z | 167.59 | 52.13  | 49.38 | 208.47 | 86684.72752 |
| 2022-02-18T17:59:21.685Z | 130.25 | 187.64 | 49.03 | 249.46 | 77344.69956 |
| 2022-02-18T09:27:41.027Z | 69.83  | 116.58 | 30.06 | 227.68 | 85319.66967 |
| 2022-02-18T00:59:22.897Z | 86.57  | 59.9   | 43    | 120.8  | 91521.50007 |
| 2022-02-17T23:59:14.741Z | 81.61  | 89.36  | 46.5  | 117.7  | 86367.99608 |
| 2022-02-17T22:59:09.892Z | 94.42  | 76.74  | 40.65 | 558    | 90158.74759 |
| 2022-02-17T14:23:59.247Z | 44.59  | 76.29  | 25    | 103.73 | 91570.66605 |
| 2022-02-17T05:59:50.665Z | 48.41  | 44.59  | 36.17 | 637.79 | 100702.6901 |
| 2022-02-16T23:59:00.563Z | 124.6  | 51.87  | 44    | 152.82 | 89986.53101 |
| 2022-02-16T19:19:16.131Z | 41.17  | 99.98  | 25    | 1210   | 89957.10624 |
| 2022-02-16T10:55:03.136Z | 68.58  | 45.47  | 32.46 | 179.07 | 87391.67587 |
| 2022-02-16T01:59:02.138Z | 143.71 | 74.25  | 55.3  | 271.93 | 71897.50421 |
| 2022-02-15T23:59:22.746Z | 74.54  | 143.73 | 34.87 | 3601   | 86498.33121 |
| 2022-02-15T15:51:01.584Z | 33.12  | 81.25  | 26    | 105.3  | 97747.39974 |
| 2022-02-15T06:59:22.695Z | 64.43  | 29.61  | 26.03 | 1333   | 95818.58439 |
| 2022-02-14T23:59:26.005Z | 71.79  | 62.86  | 36    | 234.5  | 98135.3813  |
| 2022-02-14T20:47:34.205Z | 38.56  | 63.27  | 32.81 | 889    | 93574.1566  |
| 2022-02-14T11:59:54.977Z | 49.69  | 38.56  | 24    | 68.69  | 91716.77474 |
| 2022-02-14T03:19:30.774Z | 56.65  | 49.69  | 25    | 701    | 92142.80861 |
| 2022-02-13T23:59:54.314Z | 60     | 56.65  | 29.27 | 176.83 | 97301.93399 |
| 2022-02-13T16:59:04.394Z | 38.98  | 63.86  | 25    | 122.74 | 96590.26149 |
| 2022-02-13T08:15:19.410Z | 85.13  | 35.79  | 25    | 1000   | 106331.2909 |
| 2022-02-12T23:59:49.439Z | 77.57  | 73.51  | 31.92 | 167.26 | 111650.2253 |
| 2022-02-12T21:59:35.971Z | 35.07  | 67.31  | 28    | 130.33 | 97631.35225 |
| 2022-02-12T13:11:38.358Z | 50.75  | 35.07  | 26    | 73.65  | 94410.7122  |
| 2022-02-12T04:47:59.389Z | 48.19  | 56.88  | 38.77 | 325.06 | 90907.8199  |
| 2022-02-11T23:59:18.882Z | 80.17  | 43.58  | 38.14 | 200.29 | 94199.97834 |
| 2022-02-11T18:07:53.072Z | 41.33  | 89.68  | 29.45 | 137.3  | 90947.46343 |
| 2022-02-11T09:43:11.244Z | 84.65  | 42.02  | 31    | 828.47 | 90456.04155 |
| 2022-02-11T00:59:01.078Z | 94.3   | 104.61 | 61.23 | 155.81 | 99438.36202 |
| 2022-02-10T23:59:57.488Z | 164.68 | 78.37  | 60    | 199.2  | 96516.24222 |
| 2022-02-10T23:03:48.041Z | 125.69 | 204.27 | 48.17 | 5555   | 91806.25146 |
| 2022-02-10T14:39:54.058Z | 47.63  | 123.22 | 31.86 | 166.8  | 85004.73913 |
| 2022-02-10T05:59:39.705Z | 94.22  | 40.95  | 36.3  | 195.97 | 90110.9179  |
| 2022-02-09T23:59:40.676Z | 348.72 | 94.22  | 48.93 | 487.2  | 85356.66957 |

**open, close, low, high**: Different ranges of gas prices consumed for the defined timestamp till the last timestamp

**timestamp**: timestamp of the data

**avgGas**: Average gas units consumed by a transaction

### Examples of variable gas fees for different transactions

We will be taking three examples here to understand the breakdown of gas fees for three different types of transactions

1. ETH transfer
2. USDT(ERC20 token) transfer
3. Uniswap V3 swap

For setting a standard during comparison, we will be taking the gas price as current gas price of 130 Gwei and ETH price as current price of $ 2623.

### Gas Price Example

#### 1.  ETH transfer

We know from Ethereum’s yellow paper that for ETH transfer exactly 21000 gas units are used.

**Theoretical gas price**

So using the current gas price and current ETH value, Gas fees = gas used \* gas price = 21000 \* 130 = 2730000 Gwei or 0.00273 ETH = $ 7.16

**Actual gas price**

![Eth Transfer estimate from Etherscan](https://lh3.googleusercontent.com/rQKSPJnn8Ai\_Z1wQbH2Uyz\_S0zr7DpGlFjO7cs\_KyvH71KVcsmP6oWnYRlK-pi4z3aBpEGfAt4GJp\_HGyt0S5VhRFXcZ02oQe9trBvsjsmWUuELV0vWAITA0zD5Qo7j3VSWlNMw)

#### **2.** USDT(ERC20 token) transfer

While it is very difficult to predict exact gas used for a transaction(due to factors such as account types, different transfer call methods), USDT transfer on average takes around 45000 to 65000 units of gas, so we will be considering 55000 as gas units used for our calculations.

Theoretical gas price

So using the current gas price and current ETH value, Gas fees = gas used \* gas price = 55000 \* 130 = 7150000 Gwei or 0.00715 ETH = $ 18.75

Actual gas price

![USDT Transfer Estimate from Etherscan](https://lh6.googleusercontent.com/AToQblkpYiP6JE2Q56jp2xk2Iw6BW1aSXZnludnrmg8yCYj6BU2ODiEi1BT5v9kKJ8O3PORxqEh5MTk41KGA5LWy\_S1v4bUFPOVtp57N3-VNv8NbBsFSpCepmKLTLAua3QnccXk)

#### 3. Uniswap V3 Swap

Again it is very difficult to predict the gas units for a Uniswap V3 swap as it depends on the number of factors such as type of tokens, method calls, etc, we will be taking 190000 as the average amount of gas units for a normal Uniswap V3 swap.

Theoretical gas price

So using the current gas price and current ETH value, Gas fees = gas used \* gas price = 190000 \* 130 = 24700000 Gwei or 0.0247 ETH = $ 64.78

Actual gas price

![Uniswap V3 Swap estimate from Etherescan](https://lh6.googleusercontent.com/xDQN741pY2scoWy4L30OfY7pQ7mxMUpzvTnNfq\_puqucCKomJrNaYHhBytCvN2G\_GBjedcetcMau3v2HNdy73NNtgVHQoNDZkkSjk3lUIGH32Hdr60fvxsJRkzJAP-ksS8pJ3\_Y)

## Contributors

| Discord Handle   | ETH Address                                    | Reward           | Contribution     |
| ---------------- | ---------------------------------------------- | ---------------- | ---------------- |
| **airboom#0400** | **0x84eAF08c13E86cD1603Bb8de7f5F61Fa115771bc** | 0 CMK (internal) | Original version |


# TVL Methodology 1.0

## Executive Summary

Due to the fragmented and diverse nature of DeFi, it becomes difficult to compare performance across different decentralized organizations (DAOs). The current methodology defines a standard for total value locked metric for the most basic and fundamental DeFi activities, which are lending and liquidity providing.

## Background

Total value locked (TVL) is the value of crypto assets deposited in a decentralized finance (DeFi) protocol – or in DeFi protocols generally \[1]. It’s a key metric for capturing interest in each particular platform and comparison across others. TVL includes all the coins deposited in all of the activities that DeFi protocols offer, including staking, lending and liquidity providing.

One of the challenges present across DeFi ecosystem is the difference in definitions which makes comparison difficult. Another challenge is bad acting where organizations deliberately inflate TVL numbers for marketing purposes, for example, by including leverage or assets that are not locked in lending protocols.

The following sections list details on the calculation of TVL across major DeFi activities.

### Lending

Lending/borrowing protocols TVL is defined by major DeFi players \[2,3] as

![](<../../../.gitbook/assets/image (13).png>)

### Liquidity Providing (Variation 1)

For decentralized exchanges (DEXs), TVL is defined differently. The first variation is the sum of assets in automatic market marking (AMM) pools and order book \[4]:

![](<../../../.gitbook/assets/image (11).png>)

### Liquidity Providing (Variation 2)

The second definition for DEX TVL is only the sum of all assets value in all AMM pools \[5]:

![](<../../../.gitbook/assets/image (10).png>)

Note that TVL for Variation 1 and Variation 2 are summed-up across all chains, for example Euthereum, Cardano and Solana.

## TVL Usage

TVL is used to compare different platforms and shows how valuable is each platform. DEXs TVLs are normally compared within same type, for example within between lending protocols \[6].

### Market Cap / TVL Ratio

Another useful application is TVL ratio. It shows how much of market capitalization is locked up in protocol. The lower the number, the better, as it’s best to have higher TVL and lower market capitalization as a good investment opportunity.

Let's have a look at at an example as of 21 February 2022 \[7]:

AAVE Market Cap: $1,724,949,276 Fully Diluted Valuation: $2,026,357,215 Total Value Locked (TVL): $11,510,859,312 Market Cap / TVL Ratio: 0.15 Fully Diluted Valuation / TVL Ratio: 0.176

A ratio of more than 1.0 refers to its market cap being greater than its total value locked.

## TVL Methodology 1.0&#x20;

Based on the performed analysis it’s recommended to use the following formulas for lending protocols, DEXs and mix of both, that is sometimes referred to as yield farming.&#x20;

### Lending Protocols&#x20;

For Lending/Borrowing Protocols TVL is defined as:

![](<../../../.gitbook/assets/image (8).png>)

Estimating TVL as a net exposure compared to total liabilities will reduce room for misrepresentation and manipulation of the value. For example, if $150 of asset X is deposited to a lending protocol of which $100 is then borrowed, the TVL will be $50.

### DEXs

The TVL of DEXs is recommended to use Variantion 2 mentioned above, so include only the assets values that are contained in the AMM pools. Large out of the market orders might discord TVL metric and its purpose hence it makes sense to exclude order book from the calculation.

## References

1. Coindesk, accessed on 3 March 2022\
   https://www.coindesk.com/learn/why-tvl-matters-in-defi-total-value-locked-explained/#:\~:text=Total%20value%20locked%20(TVL)%20is,sector%20of%20the%20crypto%20industry.
2. DefiLlama, accessed on 3 March 2022\
   https://defillama.com/protocol/aave
3. DefiLlama, accessed on 3 March 2022 \
   https://github.com/DefiLlama/DefiLlama-Adapters/blob/main/projects/aave/index.js
4. DefiLlama, accessed on 3 March 2022\
   https://github.com/DefiLlama/DefiLlama-Adapters/blob/main/projects/sundaeswap/index.js
5. DefiLlama, accessed on 3 March 2022\
   https://defillama.com/protocol/pancakeswap
6. Kirobo, accessed on 4 March 2022\
   https://www.kirobo.io/what-is-total-value-locked/

## Contributors&#x20;

| Discord Handle | ETH Address                                | Reward           | Contribution     | Date         |
| -------------- | ------------------------------------------ | ---------------- | ---------------- | ------------ |
| atulemis#0983  | 0x5fb7584838fB467e90bb8a1df3a278482e34E856 | 0 CMK (internal) | Original version | 7 March 2022 |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 CMK (internal) | Original version | 7 March 2022 |


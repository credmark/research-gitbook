# Uniswap V2

Uniswap is an on-chain liquidity protocol on the Ethereum blockchain that enables trustless token swaps, meaning all transactions are executed from smart contracts without the need for an intermediary or trusted party. This decentralized approach to swapping tokens has proven popular with ERC20 token holders to exchange their tokens and provide liquidity to token pairs. Uniswap launched its second iteration on the Ethereum Mainnet on the 19th May 2020 to coincide with the core contract v1.0.1 release, after testing on the Rinkeby testnet for some time prior to this.\[1]&#x20;

## 1. Is It a Protocol or Token?

Both Protocol and Token. Uniswap has a token named UNI whose distribution is decided by Uniswap Governance. The Uniswap token enables community ownership and active stewardship of the Protocol. UNI holders govern the Protocol through an on-chain governance process \[1].

## 2. Category&#x20;

**AMM, DEX** It's an AMM i.e automatic market maker. The protocol facilitates automated transactions between cryptocurrency tokens on the Ethereum blockchain through the use of smart contracts. Using a constant product formula

Token0price \*token1price = Constant

## 3. Does it have TVL?&#x20;

**Yes, total TVL is $9.7 bln. as of 14 February 2022 \[4].**

The Uniswapv2 has the following distribution of TVL as of 14 February 2022 \[4].

Ethereum: $9.7bln

Current values can be found [here](https://dappradar.com/ethereum/exchanges/uniswap-1) \[4].

## 4. Provide the following information at a protocol and pool level where appropriate.

As of 14 Feb 2022:

* Assets Not applicable
* &#x20;Liabilities Not applicable&#x20;
* Reserves Not available&#x20;
* Treasury Not available&#x20;
* Market Cap 10.94 bln \[4]&#x20;
* Ratio of Reserves to TVL (deposits only; unleveraged) Not available&#x20;
* Ratio of Treasury to TVL (deposits only; unleveraged) Not Available&#x20;
* Ratio of native Market Cap to TVL (deposits only; unleveraged) 1.12 \[4]&#x20;
* Are they double-counting leverage? - NO

## 5. Further details on the Token?

**Markets where it’s available?**&#x20;

Here are the most traded markets for Uniswap Token by volume:&#x20;

* OKX
* CoinBase Pro&#x20;
* Binance&#x20;

The full list of markets can be found [here](https://coinranking.com/coin/\_H5FVG9iW+uniswap-uni/markets?page=1) \[24].

**Liquidity**: Circulating Supply -  current numbers [here](https://www.coingecko.com/en/coins/uniswap) \[27].

**Total Supply** - on-chain supply minus burned tokens - current numbers [here](https://www.coingecko.com/en/coins/uniswap) \[27].

**Max Supply** - theoretical maximum - current numbers [here](https://www.coingecko.com/en/coins/uniswap) \[27].

## 6. What chain is it on?&#x20;

Uniswap v2 is on the Ethereum main chain only.

## 7. Could it be exploited?&#x20;

No, Uniswap v2 has never compromised but its predecessor Uniswap v1 has been, Uniswap v1 has been exploited earlier via Reentrant microtrading by exploiting ERC 777 tokens. Due to heavy reliance of Uniswap on ERC 777 \[8].

## 8. What assets does it support?&#x20;

Uniswap v2 Supports the majority of popular assets with Ether being the top traded. The list of supported assets for v3 can be found here \[9].

## 9. How does it combine the risks of those assets?

Uniswap v2 from a LP provider perspective gives the HODL exposure, generated fees, and Impermanent Loss (IL). Below is the IL curve for Uniswap v2 for a similar priced assets pool \[23]. Below graph shows the dependency between IL on the vertical axis to the ratio of current value to original value on the horizontal axis.

![](https://lh6.googleusercontent.com/xQ2\_q7D\_yz-WmpiN9FoLbwCzmCp\_sejEPWtJE\_okV7hlAwoCWQ0OGMJA7mloerfI8fFxGT0mnZyb5\_nx606mQn5Xpxf3Vu4qs30PQSAE53IXZ\_HoEIHNoZ27FoBRsQ)

## 10. Does it wrap and distribute assets?

Yes, it wraps assets.

The Uniswap v2 Protocol supports trading of ERC20 tokens. In order to swap a native asset like ETH, the Uniswap protocol wraps these assets in an ERC20 wrapped native token contract. The protocol uses the following WETH9 addresses on Ethereum. For example, Wrapping ether allows the direct, seamless exchange between ether and ERC-20 tokens without the need for a trusted third party and without incurring unnecessary risks such as unexpected errors during transactions.

## 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

There are no liquidations in Uniswap v2.&#x20;

## 12. What are the dependencies of the protocol? How does risk bubble up?&#x20;

Uniswap v2 does not have any dependencies on any third-party apps or APIs\[8].

## 13. Does it have a governance token&#x20;

Yes, its name is UNI.&#x20;

UNI holders are responsible for ensuring that governance decisions are made in compliance with applicable laws and regulations. To help facilitate this, the fee switch has been initialized to a contract UNI holders can use to vote on tokens for which they will collect fees. The community is encouraged to consult knowledgeable legal and regulatory professionals before implementing any specific proposal \[26].&#x20;

## 14. How decentralized is it?

Uniswap is the largest decentralized exchange (or DEX) operating on the Ethereum blockchain. It allows users anywhere in the world to trade crypto without an intermediary. UNI, the governance token that allows users to vote on key protocol changes. As a governance token, UNI entitles holders to a vote in how the protocol is run, affording them immediate ownership of Uniswap governance, the UNI community treasury, the protocol fee switch, eth ENS, the Uniswap Default List (tokens.uniswap.eth) and SOCKS liquidity tokens. The token was quickly listed on the Coinbase Pro exchange, and soon after on the main Coinbase exchange \[14].

## 15. Additional Information&#x20;

**VAR** - VaR could be applied to manage risk of LPing from a LP provider perspective

**LCR** - Not applicable&#x20;

**Are there any other metrics that might be useful?**&#x20;

**Sharpe Ratio** - could be useful when applied to the UNI token market behaviour&#x20;

**Annual percentage yield(APY)** - APY is an important metric that any liquidity provider or investor should follow in Uniswap. APY provides a real rate of return earned on a liquidity pool into account the effect of compounding interest. The below curve highlights the 12-hour and 24-hour APY which provides an idea of the opportunity for liquidity providers in any given pool \[23].

## 16. How is this exposed to layers in Defi

**What layers are upstream (built on top of the protocol)? Are there other protocols that use it as a source of data/pricing oracle, or put funds into it?**&#x20;

There are Dapps that use Uniswap. Though there are no apps that interact with UNI token internally or use it to facilitate any operations internally, Uniswap integrations can be found in many apps mostly for maximizing returns with charm finance being the most popular one. The full list of apps can be found here \[15].

What layers are downstream (protocols/assets built on or put into the platform). For example, yield farms are built on top of lending protocols &#x20;

Uniswapv2 is not downstreaming data from anywhere.

## 17. Smart Contract information

**Uniswap v2 protocol address**: &#x20;

[https://etherscan.io/address/0x5C69bEe701ef814a2B6a3EDD4B1652CB9cc5aA6f](https://etherscan.io/address/0x5C69bEe701ef814a2B6a3EDD4B1652CB9cc5aA6f)\[16].&#x20;

**UNI token tracker address**:&#x20;

[0x1f9840a85d5af5bf1d1762f925bdaddc4201f984](https://etherscan.io/token/0x1f9840a85d5af5bf1d1762f925bdaddc4201f984) \[17].&#x20;

**Are there any other relevant smart contracts?** Yes, all the pools in the Uniswap v2 have an address associated with it. List of all pools can be found [here](https://v2.info.uniswap.org/home) \[18].

## References

1. Medium, https://rossbulat.medium.com/uniswap-v2-everything-new-with-the-decentralised-exchange52b4bb2093ab#:\~:text=Uniswap%20V2%20is%20the%20next,an%20intermediary%20or%20trusted%20party.&#x20;
2. Uniswap, https://docs.uniswap.org/protocol/concepts/V3-overview/concentrated-liquidity&#x20;
3. Levelup, https://levelup.gitconnected.com/whats-new-in-uniswap-v3-a04a8f2673bb&#x20;
4. Dappradar, https://dappradar.com/ethereum/exchanges/uniswap-1
5. Coinmarketcap, https://coinmarketcap.com/currencies/uniswap/&#x20;
6. Dune, https://dune.xyz/queries/56987&#x20;
7. CoinBase, https://www.coinbase.com/price/uniswap&#x20;
8. Siliconangle, https://siliconangle.com/2020/04/19/25m-cryptocurrency-stolen-hack-lendf-uniswap/&#x20;
9. Uniswap, https://info.uniswap.org/#/&#x20;
10. Credmark, https://credmark.com/&#x20;
11. Uniswap, https://docs.uniswap.org/protocol/reference/deployments&#x20;
12. Uniswap, https://help.uniswap.org/en/articles/5455536-do-i-get-liquidated-if-the-price-goes-outside-of-my-range&#x20;
13. Uniswap, https://uniswap.org/whitepaper-v3.pdf&#x20;
14. Decrypt, https://decrypt.co/resources/what-is-uniswap&#x20;
15. Uniswap, https://uniswap.org/ecosystem&#x20;
16. Etherscan, https://etherscan.io/address/0x5C69bEe701ef814a2B6a3EDD4B1652CB9cc5aA6f
17. Etherscan, https://etherscan.io/address/0x1f9840a85d5af5bf1d1762f925bdaddc4201f984&#x20;
18. Uniswap, https://v2.info.uniswap.org/home
19. Coingecko, https://www.coingecko.com/en/coins/uniswap&#x20;
20. Coinmarketcap, https://coinmarketcap.com/exchanges/uniswap-v2/&#x20;
21. DefiLlama, https://github.com/DefiLlama/DefiLlama-Adapters/blob/main/projects/uniswap/index.js&#x20;
22. Charm, https://charm.fi/&#x20;
23. Medium, https://medium.com/intotheblock/some-cool-indicators-about-uniswap-that-defi-traders-and-investors-should-know-about-6e5138516273&#x20;
24. Coinranking, https://coinranking.com/coin/\_H5FVG9iW+uniswap-uni/markets?page=1&#x20;
25. Blockscribers, https://www.blockscribers.com/article/uniswap-v1-vs-v2-vs-v3/10/&#x20;
26. Uniswap, https://uniswap.org/blog/uni
27. Coingecko, https://www.coingecko.com/en/coins/uniswap



| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| Deadsec        | 0x1A2E1d4553d33c080746A056AA3F832823fADB51 | 0 $CMK (internal) | Original version |

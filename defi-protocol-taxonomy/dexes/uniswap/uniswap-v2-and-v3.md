# Uniswap V2 and V3

Uniswap is a cryptocurrency exchange which uses a decentralized network protocol. Uniswap is also the name of the company that initially built the Uniswap protocol. The protocol facilitates automated transactions between cryptocurrency tokens mainly on the Ethereum blockchain through the use of smart contracts \[1].Uniswap v3, have been released on May 5, 2021. Uniswap v3, when compared to v2, provides better capital efficiency and accuracy. The fee structure is very flexible. The Liquidity providers can get high returns on their capital to provide liquidity with 4000x capital efficiency compared to v2. The main goal of Uniswap v3 was to surpass stablecoin-based AMMs and centralized exchanges by facilitating low-slippage trade execution \[25].

### 1. Is It a Protocol or Token?

Both Protocol and Token. Uniswap has a token named UNI whose distribution is decided by Uniswap Governance.The Uniswap token enables community ownership and active stewardship of the Protocol. UNI holders govern the Protocol through an on-chain governance process \[1].

### 2. Category&#x20;

AMM,DEX It's an AMM i.e automatic market maker.The protocol facilitates automated transactions between cryptocurrency tokens on the Ethereum blockchain through the use of smart contracts. Using a constant product formula

Token0price \*token1price = Constant (same for both v2 and v3)

Uniswapv3 introduces “concentrated liquidity”.Concentrated liquidity serves as a mechanism to let the market decide what a sensible distribution of liquidity is, as rational LPs are incentivized to concentrate their liquidity while ensuring that their liquidity remains active. To achieve concentrated liquidity, the once continuous spectrum of price space has been partitioned with ticks. Ticks are the boundaries between discrete areas in price space. Ticks are spaced such that an increase or decrease of 1 tick represents a 0.0001% increase or decrease in price at any point in price space.&#x20;

&#x20;                   𝑝(𝑖) = 1.0001\*\*i (i represents the ith tick)

&#x20;                   _Introduced only in v3_

Ticks function as boundaries for liquidity positions. When a position is created, the provider must choose the lower and upper tick that will represent their position's borders. As the spot price changes during swapping, the pool contract will continuously exchange the outbound asset for the inbound, progressively using all the liquidity available within the current tick interval \[1] until the next tick is reached. At this point, the contract switches to a new tick and activates any dormant liquidity within a position that has a boundary at the newly active tick. While each pool has the same number of underlying ticks, in practice only a portion of them are able to serve as active ticks. Due to the nature of the v3 smart contracts, tick spacing is directly correlated to the swap fee. Lower fee tiers allow closer potentially active ticks, and higher fees allow a relatively wider spacing of potential active ticks. While inactive ticks have no impact on transaction cost during swaps, crossing an active tick does increase the cost of the transaction in which it is crossed, as the tick crossing will activate the liquidity within any new positions using the given tick as a border. In areas where capital efficiency is paramount, such as stable coin pairs, narrower tick spacing increases the granularity of liquidity provisioning and will likely lower price impact when swapping - the result being significantly improved prices for stable coin swaps \[2].

### **3. Does it have TVL?**&#x20;

#### Yes, total TVL is $7.96 bln as of 21 January 2022 \[4].

The Uniswapv3 has the following distribution of TVL as of 21 January 2022 \[4].

|          |              |
| -------- | ------------ |
| Ethereum | $7.78bln     |
| Optimism | $38.35mln    |
| Polygon  |  $76.42 mln  |
| Arbitrum | $39.28 mln   |

#### How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?

Their Frontend, Dune, DefiPulse - to be provided.&#x20;

DefiLlama - it is calculated by counting the tokens locked on AMM pools, pulling the data from the respective subgraphs mentioned here \[21].

### 4**.** Provide the following information at a protocol and pool level where appropriate:&#x20;

As of 21 Jan 2022&#x20;

* Assets Not applicable&#x20;
* Liabilities Not applicable&#x20;
* Reserves Not available&#x20;
* Treasury 2.517 bln \[6]&#x20;
* Market Cap 8.912 bln \[6]&#x20;
* Ratio of Reserves to TVL (deposits only; unleveraged) Not available&#x20;
* Ratio of Treasury to TVL (deposits only; unleveraged) 0.3162 \[6]\[4]
* &#x20;Ratio of native Market Cap to TVL (deposits only; unleveraged) 1.12 \[5]&#x20;
* Are they double-counting leverage? - NO

### 5. Further details on the Token?

**Markets where it’s available?**&#x20;

Here are the most traded markets for Uniswap Token by volume:&#x20;

* OKK&#x20;
* CoinBase Pro&#x20;
* Binance&#x20;

The full list of markets can be found here \[24].

**Liquidity**

* Circulating Supply - the total amount of tokens in circulation 452 mln \[19].&#x20;
* Total Supply - on-chain supply minus burned tokens 1bln \[19].&#x20;
* Max Supply - theoretical maximum as coded 1bln \[19].

### 6. What chain is it on?&#x20;

MultiChain ****&#x20;

Uniswap v2 was initially built on the Ethereum chain but now supports Optimism,Polygon and Arbitrum as well with the introduction of v3\[4].

### **7. Could it be exploited?**

Yes, Uniswapv3 has been exploited earlier via Reentrant microtrading by exploiting ERC 777 tokens.Due to heavy reliance of uniswap on ERC 777 its security has been compromised.Uniswap is believed to have lost between $300,000 and $1.1 million in imBTC tokens.According to Tokenlon, the first attack targeted Uniswap at 8 p.m. EDT Friday using an exploit that targeted ERC777, an underlying technology on the Ethereum blockchain to perform a “reentrancy” attack. That attack exploits a function that makes an external call to another untrusted contract before it resolves any effects, allowing an attacker to take over the control flow of the smart contract \[8].

### **8. What assets does it support?**

Uniswap(both v2 and v3) Supports majority of popular assets with Ether being the top traded. The list of supported assets for v3 can be found here \[9].

### 9**.** How does it combine the risks of those assets?

Uniswap v3 from a LP provider perspective gives the HODL exposure, generated fees and Impermanent Loss (IL). Below is the IL curve for Uniswapv3 for WBTC-ETH pool \[23].

![](https://lh3.googleusercontent.com/w1Rw4dwkU3XscPMcX--xAmx6CIGf2wNaWlp\_lUyoK1tE2RTKty-p8CNwqwX8TcdxPS0\_pHG3bo4w1pEDVakROT5YcOHfQuLhGQlTttJBuuu0TqnQ86DoiU9V7Dx2WoBL6V9Aex7M)

### 10. Does it wrap and distribute assets?

Yes, it wraps assets.&#x20;

The Uniswap (both v2 and v3) Protocol supports trading of ERC20 tokens. In order to swap a native asset like ETH (or MATIC on Polygon), the Uniswap protocol wraps these assets in an ERC20 wrapped native token contract. The protocol uses the following WETH9 addresses on Ethereum and WMATIC addresses on Polygon \[11]. For example Wrapping ether allows the direct, seamless exchange between ether and ERC-20 tokens without the need for a trusted third-party and without incurring in unnecessary risks such as unexpected errors during transactions.

### **11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?**

There are no liquidations in case of v2 or v3, but in v3 positions can become idle. If the price goes outside of the LP position price range, then the position will be singularly concentrated in the less valuable asset. As an example, if a price range of 1,000 — 5,000 for ETH/USDC and ETH falls to 900, then the balance will be entirely concentrated in ETH. Conversely, if ETH appreciates to 6,000, then the balance will be entirely concentrated in USDC. While the price remains outside of the price range, the position will be "inactive". This means the position will not earn fees until if and when the price comes back in range.But the impermanent loss keeps on increasing \[12].



### 12. What are the dependencies of the protocol? How does risk bubble up?

Neither Uniswap v2 nor v3 has any dependencies on any third party apps or APIs, but v3 heavily relies on ERC 777 that has been compromised in the past via Reentrant microtrading \[8].

### 13. Does it have a governance token&#x20;

Yes, its name is UNI.&#x20;

UNI governance token in v3 has more flexibility than v2 in choosing the fraction of swap fees that go to the protocol, and is able to choose any fraction 1 𝑁 where 4 ≤ 𝑁 ≤ 10, or 0. This parameter can be set on a per-pool basis. UNI governance also has the ability to add additional fee tiers. When it adds a new fee tier, it can also define the tickSpacing corresponding to that fee tier. Once a fee tier is added to the factory, it cannot be removed (and the tickSpacing cannot be changed). The initial fee tiers and tick spacings supported are 0.05% (with a tick spacing of 10, approximately 0.10% between initializable ticks), 0.30% (with a tick spacing of 60, approximately 0.60% between initializable ticks), and 1% (with a tick spacing of 200, approximately 2.02% between ticks. Finally, UNI governance has the power to transfer ownership to another address \[13].

### 14. How decentralized is

Uniswap is the largest decentralized exchange (or DEX) operating on the Ethereum blockchain. It allows users anywhere in the world to trade crypto without an intermediary. UNI, the governance token that allows users to vote on key protocol changes.As a governance token, UNI entitles holders to a vote in how the protocol is run, affording them immediate ownership of Uniswap governance, the UNI community treasury, the protocol fee switch, eth ENS, the Uniswap Default List (tokens.uniswap.eth) and SOCKS liquidity tokens. The token was quickly listed on the Coinbase Pro exchange, and soon after on the main Coinbase exchange \[14].

### **15. Additional Information**

* VAR - VaR could be applied to manage risk of LPing from a LP provider perspective
* LCR - Not applicable

&#x20; **Are there any other metrics that might be useful?Like Sharpe Ratio**

* **Sharpe Ratio** - could be useful when applied to the UNI token market behaviour
* **Annual percentage yield(APY) -** APY is an important metric that any liquidity provider or investor should follow in Uniswap. APY provides a real rate of return earned on a liquidity pool into account the effect of compounding interest.The below curve highlights the 12-hour and 24-hour APY which provides an idea of the opportunity for liquidity providers in any given pool \[23].



### 16. How is this exposed to layers in Defi:

* **What layers are upstream (built on top of the protocol)? Are there other protocols that use it as a source of data/pricing oracle, or put funds into it?**

&#x20;      There are Dapps that use uniswap. Though there are no apps that interact with UNI token     internally or uses it to facilitate any operations internally, uniswap integrations can be found inmany apps mostly for maximizing returns with charm finance being the most popular one. The full list of apps can be found here \[15].

* **What layers are downstream (protocols/assets built on or put into the platform). For example, yield farms are built on top of lending protocols**

&#x20;     Both Uniswapv2 and v3 are not sourcing data from anywhere.

### **17. Smart Contract information**

* **List the protocol´s smart contract address:** Uniswapv3 protocol address :0xE592427A0AEce92De3Edee1F18E0157C05861564 \[16].&#x20;
* **List the Token´s smart contract address UNI token tracker address:** 0x1f9840a85d5af5bf1d1762f925bdaddc4201f984 \[17].&#x20;
* **Are there any other relevant smart contracts?** Yes, all the pools in the uniswapv3 have a address associated with it with USDC / ETH (0.3%) being the most popular one 0x8ad599c3a0ff1de082011efddc58f1908eb6e6d8.List of all addresses can be found here \[18].



References:&#x20;

1. Wikipedia, https://en.wikipedia.org/wiki/Uniswap#:\~:text=Uniswap%20is%20a%20decentralized%20finance,the%20use%20of%20smart%20contracts.&#x20;
2. Uniswap, https://docs.uniswap.org/protocol/concepts/V3-overview/concentrated-liquidity&#x20;
3. Levelup, https://levelup.gitconnected.com/whats-new-in-uniswap-v3-a04a8f2673bb&#x20;
4. Defipulse, https://defillama.com/protocol/uniswap&#x20;
5. Coinmarketcap, https://coinmarketcap.com/currencies/uniswap/
6. &#x20;Dune, https://dune.xyz/queries/56987&#x20;
7. CoinBase, https://www.coinbase.com/price/uniswap&#x20;
8. Siliconangle, https://siliconangle.com/2020/04/19/25m-cryptocurrency-stolen-hack-lendf-uniswap/&#x20;
9. Uniswap, https://info.uniswap.org/#/&#x20;
10. Credmark, https://credmark.com/&#x20;
11. Uniswap, https://docs.uniswap.org/protocol/reference/deployments&#x20;
12. Uniswap, https://help.uniswap.org/en/articles/5455536-do-i-get-liquidated-if-the-price-goes-outside-of-my-range&#x20;
13. Uniswap, https://uniswap.org/whitepaper-v3.pdf
14. &#x20;Decrypt, https://decrypt.co/resources/what-is-uniswap&#x20;
15. Uniswap, https://uniswap.org/ecosystem&#x20;
16. Etherscan, https://etherscan.io/address/0xe592427a0aece92de3edee1f18e0157c05861564&#x20;
17. Etherscan, https://etherscan.io/address/0x1f9840a85d5af5bf1d1762f925bdaddc4201f984&#x20;
18. Uniswap, https://info.uniswap.org/#/&#x20;
19. Coingecko, https://www.coingecko.com/en/coins/uniswap&#x20;
20. Coinmarketcap, https://coinmarketcap.com/exchanges/uniswap-v2/&#x20;
21. DefiLlama, https://github.com/DefiLlama/DefiLlamaAdapters/blob/main/projects/uniswap/index.js
22. Charm, https://charm.fi/&#x20;
23. Medium, https://medium.com/intotheblock/some-cool-indicators-about-uniswap-that-defi-traders-and-investors-should-know-about-6e5138516273
24. Coinranking, https://coinranking.com/coin/\_H5FVG9iW+uniswap-uni/markets?page=1&#x20;
25. Blockscribers, https://www.blockscribers.com/article/uniswap-v1-vs-v2-vs-v3/10/



| Discord Handle | ETH Address                                | Reward            | Contribution     |   |   |
| -------------- | ------------------------------------------ | ----------------- | ---------------- | - | - |
| Deadsec        | 0x1A2E1d4553d33c080746A056AA3F832823fADB51 | 0 $CMK (internal) | Original version |   |   |

# Balancer

Balancer is a community-driven protocol, automated portfolio manager, liquidity provider, and price sensor that empowers decentralized exchange and the automated portfolio management of tokens.

### 1. Is It a Protocol or Token? -&#x20;

#### **Both Protocol and Token**

### 2. Category&#x20;

#### &#x20;AMM, DEX

### **3. Does it have TVL?**

Yes, total TVL is $3.01 Bln as of 24 Feb 2022 \[5].

Current numbers [here](https://defillama.com/protocol/balancer).

**How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?**

Balancer has the following distribution of TVL as of 21 Feb 2022 \[5].&#x20;

TVL(USD) is calculated by taking these balances and multiplying them by their price in USD. \[6]

| Ethereum: | $2.71b  |
| --------- | ------- |
| Polygon:  | $219.6m |
| Arbitrum: | $73.48m |

### 4. What are it’s core metrics?

As of 25 Febuary 2022:

* Liabilities ?&#x20;
* Assets ?&#x20;
* Reserves ?
* Treasury ?
* Ratio of Reserves to TVL (deposits only; unleveraged) ?
* Ratio of Treasury to TVL (deposits only; unleveraged) ?&#x20;
* Ratio of native Market Cap to TVL (deposits only; unleveraged) ?
* Are they double-counting leverage? ?

### **5. Further details on the Token?**

Markets where it’s available?&#x20;

Top exchanges that support $BAL include Binance, ZenGo, Global, HBTC, Kraken, OKEx, Huobi, etc. \[8]

Liquidity:&#x20;

* Circulating Supply - the total amount of tokens in circulation - 6.94 mln \[x]&#x20;
* Total Supply - on-chain supply minus burned tokens - 35.7 mln \[x]
* Max Supply - theoretical maximum as coded - 1 bln \[x]

### **6: What chain is it on?**

Multichain.&#x20;

Balancer was initially built on the Ethereum chain but now supports Polygon and Arbitrum as well \[4].

### 7. Could it be exploited?

Yes&#x20;

#### Is it Cross Chain?&#x20;

Yes,&#x20;

The Balancer automated market maker protocol was hacked for over $500,000 in a single Ether (ETH) transaction, facilitated once again by a dYdX flash loan in June 2020. The transaction began with a flash loan from dYdX for 104,000 ETH, or about $23 million. The exploit relied on Statera (STA), a deflationary token where 1% of every transaction is automatically burned. Balancer’s smart contracts seem to have failed to account for this, thus expecting that each transaction would be for the full amount. The hacker exploited this by exchanging back and forth between Statera and Ether 24 times. At each step, the STA balance available to the contract diminished by 1%, but the smart contract did not account for this. Thus, the price of STA remained stable despite the dwindling supply. \[10]

### 8. What assets does it support?

Balancer Supports majority of popular assets with USDT being the top traded. The list of supported assets for v3 can be found here \[12].

### 9. How does it combine the risks of those assets?

#### Borrow/Lend Exposure

Balancer from a LP provider perspective gives Impermanent Loss (IL), although lesser than other protocol Thanks to the possibility of creating unequal pools. Below is the IL curve for Balancer \[13].

![](<../../.gitbook/assets/Screenshot 2022-02-25 at 1.50.36 AM.png>)

### 10. Does it wrap and distribute assets?

No it does not wrap assets.

### 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

To be updated

### 12. What are the dependencies of the protocol? How does risk bubble up?

Balancer is dependent on yarn \[14]

### **13. Does it have a governance token?**

Balancer's BAL token acts as a governance token to help the project set features such as issuance rewards and whitelisted pools for liquidity mining. \[9]

### **14. How decentralized is**

Balancer Governance is the heart and brain of Balancer Protocol. Anyone who holds a BAL token becomes part of the Balancer Governance. The more tokens you have, the stronger your voice is. Governance makes decisions about new features, directions of where the Balancer Protocol should go and looks over the Balancer Community. The Governance is the ultimate decision-body for Balancer Protocol, no one can override the Governance’s vote result. The main responsibilities of Balancer Governance are voting on new proposals on changes to the Balancer community and deciding on whether/how the protocol fees will be used. \[x]

### 15. Additional Information VAR

* **VaR** - ?
* **LCR** - ?
* **Are there any other metrics that might be useful? Like Sharpe Ratio** - ?



### 16. How is this exposed to layers in DeFi:

#### What layers are upstream (built on top of the protocol)?

NA

#### What layers are downstream (protocols/assets built on or put into the platform). For example, yield farms are built on top of lending protocols

NA

### 17. Smart Contract information

**List the protocol´s smart contract address**&#x20;

[Balancer protocol address](https://dev.balancer.fi/references/contracts/contract-addresses) \[22].&#x20;

**List the Token´s smart contract address** &#x20;

[0xba100000625a3754423978a60c9317c58a424e3D](https://etherscan.io/token/0xba100000625a3754423978a60c9317c58a424e3d) \[19].&#x20;

**Are there any other relevant smart contracts?**\
****[Overview of Balancer Pools](https://pools.balancer.exchange/#/explore).



## References

1. Kraken, https://www.kraken.com/learn/what-is-balancer-bal
2. Balancer, https://docs.balancer.fi/
3. Coinbase, https://www.coinbase.com/price/balancer#:\~:text=Balancer%20(BAL)%20is%20an%20Ethereum,while%20earning%20customizable%20trading%20fees
4. Coinmarketcap, https://coinmarketcap.com/alexandria/article/what-is-balancer
5. Defillama, https://defillama.com/protocol/balancer
6. Defiyield, https://blog.defiyield.app/what-is-total-value-locked-tvl-583d85ad8ba2
7. Coinbase, https://www.coinbase.com/price/balancer
8. Coinmarketcap, https://coinmarketcap.com/currencies/balancer/
9. Binanace, https://research.binance.com/en/projects/balancer
10. Cointelegraph, https://cointelegraph.com/news/defi-protocol-balancer-hacked-through-exploit-it-seemingly-knew-about
11. Yahoo, [https://finance.yahoo.com/news/defi-deep-dive-balancing-crypto-093000741.html#:\~:text=Balancer%20derives%20its%20name%20from,into%20to%20its%20custom%20pools.\&text=Liquidity%20providers%20who%20own%20Balancer,assets%20on%20the%20open%20market](https://finance.yahoo.com/news/defi-deep-dive-balancing-crypto-093000741.html#:\~:text=Balancer%20derives%20its%20name%20from,into%20to%20its%20custom%20pools.\&text=Liquidity%20providers%20who%20own%20Balancer,assets%20on%20the%20open%20market)
12. Dune, https://dune.xyz/balancerlabs/Balancer-VolumDunee-Token-Breakdown
13. Medium, [https://arnauramiomateu.medium.com/understanding-balancer-protocol-frmo-0-to-100-998ba20c6834](https://arnauramiomateu.medium.com/understanding-balancer-protocol-frmo-0-to-100-998ba20c6834)
14. Finboid, https://finbold.com/review/balancer-review/
15. Github, https://github.com/balancer-labs/balancer-core
16. Balancer, https://docs.balancer.fi/getting-started/faqs/governance
17. Bravenewcoin, https://bravenewcoin.com/insights/balancer-price-analysis-open-ended-automated-market-maker-pools
18. Balancer, https://docs.balancer.fi/products/balancer-pools
19. Etherscan, https://etherscan.io/token/0xba100000625a3754423978a60c9317c58a424e3D
20. Balancer, https://docs.balancer.fi/products/merkle-orchard#addresses
21. Balancer, [https://docs.balancer.fi/ecosystem/governance/bal-governance-token#contract-address](https://docs.balancer.fi/ecosystem/governance/bal-governance-token#contract-address)
22. Balancer, [https://dev.balancer.fi/references/contracts/contract-addresses](https://dev.balancer.fi/references/contracts/contract-addresses)

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 $CMK (internal) | Original version |


# Sushiswap

SushiSwap was launched in September 2020 by two anonymous developers called Chef Nomi and 0xMaki. It is one of the most popular Decentralized Applications (DApp) on the Ethereum blockchain. SushiSwap adopts the automated market-making (AMM) model for its decentralized exchange (DEX) protocol.

### 1. Is It a Protocol or Token? -&#x20;

Both Protocol and Token

### 2. Category&#x20;

DEX

### **3. Does it have TVL?**

Yes its  $10.81 bln as of 27th Feb 2022 \[1].

**How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?**

* Frontend: No information available. \[2].
* Dune: No information available.
* Defipulse: $1.56 bln \[3].
* Defillama: $10.81 bln. \[1].

TVL distribution across multiple chains \[1].

| Chains               | Value        |
| -------------------- | ------------ |
| Moonriver            | $29.86 mln   |
| Avalanche            | $215.01 mln  |
| Ethereum             | $2.6 bln     |
| Harmony              | $59.45 mln   |
| BSC                  | $39.97 mln   |
| Gnosis               | $16.61 mln   |
| Heco                 | $145.92      |
| Telos                | $3.6 mln     |
| Celo                 | $22.06 mln   |
| Borrowed             | $6.6b        |
| Fuse                 | $1.47 mln    |
| Fantom               | $134.58 mln  |
| Staking              | $232.44 mln  |
| OKExChain            | $56.72 k     |
| PalmPalm             | $583.97      |
| Polygon              | $244.83 mln  |
| Arbitrum             | $622.77 mln  |

### 4. What are it’s core metrics?

* Liabilities:   Not available.
* Assets:  Not available.
* Reserves: Not available.
* Treasury:  $33 mln \[4].
* Market Cap Native:  $0.62 bln \[5].
* Ratio of Reserves to TVL (deposits only; unleveraged) Not available.
* Ratio of Treasury to ingleTVL (deposits only; unleveraged) : 0.0030.
* Ratio of native Market Cap to TVL (deposits only; unleveraged) : 0.0573.
* Are they double-counting leverage? No.

### **5. Further details on the Token?**

Markets where it’s available? Sushi is traded on 93 exchanges \[6].

Top exchanges:

* FTX ($21.83M)
* HitBTC ($11.16M)
* Binance ($10.84M)

Liquidity \[5] :&#x20;

* Supply - the total amount of tokens in circulation : 192.7 mln.
* Total Supply - on-chain supply minus burned tokens :  241 mln.
* Max Supply - theoretical maximum as coded : 250 mln.

### **6: What chain is it on?**

**MultiChain**

Majorly on Fantom, Polygon, xDai chain, Binance, Moonbeam \[7] with support for 10+ blockchains.&#x20;

Whilst adoption remains dominant on the Ethereum mainchain, Polygon now makes up \~20% of Sushi's DEX volume.

Sushi deployments on other chains are fairly underutilized for now \[8].

### 7. Could it be exploited?

Yes&#x20;

Recently, a white hacker discovered a vulnerability that, if exploited, could have resulted in all of the crypto assets in the token auction contract being drained by a malicious actor. An attacker could reuse the same ETH over and over to batch multiple calls to the contract and “bid in the auction for free.” He also discovered that a hacker could steal the funds from the contract by triggering a refund by sending a higher amount of ETH than the auction hard cap \[9].

But on 18 Sept 2021, SushiSwap’s token platform called MISO was reportedly attacked on Thursday, with the hacker stealing 864.8 Ethereum, approximately $3 million in current prices. MISO fell victim to a so-called supply chain attack, which saw an anonymous contractor going under the GitHub handle _AristoK3_ inject malicious code into the platform’s front end and replace the auction’s wallet with their own address \[10].

### 8. What assets does it support?

Sushiswap supports majority of popular assets with USDC being the top traded. The list of supported assets for v3 can be found here \[11].

### 9. How does it combine the risks of those assets?

The only real disadvantages to SushiSwap at this point are impermanent loss and if you are less bullish on SUSHI than ETH because it you use SushiSwap, 0.05% of the 0.3% fees you receive will be in SUSHI, whereas on Uniswap the entirety of the 0.3% fee portion you receive is in ETH. Otherwise, the platforms are essentially the same in terms of security and asset availability \[12].

### 10. Does it wrap and distribute assets?

No, it does not wrap assets

### 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

Assets are not liquidated as no collateral is involved.&#x20;

### 12. What are the dependencies of the protocol? How does risk bubble up?

Dependent on node v10 and yarn \[13].

### **13. Does it have a governance token?**

xSUSHI is a governance token, that means xSUSHI holders are able to participate in voting decisions on upgrades and future changes on the Sushi platform. By staking SUSHI locked for 6 months, Liquidity Providers are rewarded with xSUSHI. The indispensable advantage of xSUSHI is that holders are rewarded with 0.05% of Tx Fees **** \[14]. SUSHIPOWAH is our voting metric, and is decided as follows:

1. Each SUSHI in the SUSHI-ETH pool is worth 2 SUSHIPOWAH
2. Each SUSHI held via xSUSHI tokens equal 1 SUSHIPOWAH

### **14. How decentralized is Sushiswap**

SushiSwap is ultimately governed by its community, via forum discussions and, when pertinent, voting on proposals held on the SushiSwap Snapshot. At this time, only proposals posted to the Snapshot voting system by the CORE can be considered binding if passed with a quorum.&#x20;

* Total Users: 845,333 \[15].
* SUSHI Token Holders: 74,557 \[15].
* Top SUSHI holders \[15].
  * SushiBar (Staked Sushi)
  * Treasury
  * SushiSwap SUSHI/ETH LP (SLP)
  * 0xcBE6B83e77cdc011Cc18F6f0Df8444E5783ed982
  * Binance
  * Huobi
  * 0x2d615795a8bdb804541C69798F13331126BA0c09
  * 0x47ac0Fb4F2D84898e4D9E7b4DaB3C24507a6D503
  * Binance
  * 0x80845058350B8c3Df5c3015d8a717D64B3bF9267

### 15. Additional Information VAR

* **VaR** - To be updated
* **LCR** - To be updated
* **Are there any other metrics that might be useful? Like Sharpe Ratio** - To be updated

### 16. How is this exposed to layers in DeFi:

#### What layers are upstream (built on top of the protocol)?

To be updated

#### What layers are downstream (protocols/assets built on or put into the platform). For example, yield farms are built on top of lending protocols?

Uniswap v2

### 17. Smart Contract information

#### &#x20;List the protocol´s smart contract address ?

To be updated

#### List the Token´s smart contract address ?

To be updated

#### Are there any other relevant smart contracts?

To be updated



## References

1. Defillama, https://defillama.com/protocol/sushiswap&#x20;
2. Sushiswap, https://analytics.sushi.com/&#x20;
3. Defipulse, https://www.defipulse.com/projects/sushiswap&#x20;
4. Etherscan, https://etherscan.io/token/0x6b3595068778dd592e39a122f4f5a5cf09c90fe2?a=0xe94b5eec1fa96ceecbd33ef5baa8d00e4493f4f3&#x20;
5. Coingecko, https://www.coingecko.com/en/coins/sushi&#x20;
6. Nomics, http://nomics.com/assets/sushi-sushi#text=available%20on%20Uniswap.-,Disadvantages%20of%20SushiSwap,you%20receive%20is%20in%20ETH.
7. Twitter, https://twitter.com/josephdelong/status/1367226781393166336&#x20;
8. Glassnode, https://insights.glassnode.com/defi-uncovered-exploring-the-sushi-ecosystem/
9. Cointelegraph, https://cointelegraph.com/news/white-hat-potentially-saves-sushiswap-350m-by-finding-obvious-exploit.&#x20;
10. Sushiswap, https://docs.sushi.com/governance/current-governance-model.&#x20;
11. Coinmarketcap, https://coinmarketcap.com/currencies/sushiswap/&#x20;
12. Cryptovantage, https://www.cryptovantage.com/buying-crypto/sushiswap/#:\~:text=available%20on%20Uniswap.-,Disadvantages%20of%20SushiSwap,you%20receive%20is%20in%20ETH.&#x20;
13. Github, https://github.com/sushiswap&#x20;
14. Coin98insights, https://coin98insights.com/sushiswap-sushi&#x20;
15. Dune, https://dune.xyz/dqniellew/Sushiswap

****





****

****

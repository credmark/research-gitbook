# MakerDAO

MakerDAO is a Decentralized Finance (DeFi) project with a crypto-collateralized stablecoin, called  DAI, that is aims to hold a 1:1 peg to the US dollar. Its community manages the protocol and the token via a Decentralized Autonomous Organization (DAO).

### 1. Is it a Protocol or Token?

Both a Protocol as well as a Token.

The Maker Protocol is also known as the Multi-Collateral DAI (MCD) system, and it allows users to generate DAI by leveraging collateral assets approved by “_Maker Governance_.”&#x20;

DAI is a decentralized, unbiased, collateral-backed cryptocurrency and soft-pegged to the US Dollar. Resistant to hyperinflation due to its low volatility, DAI offers economic freedom and opportunity to anyone, anywhere \[1].

MKR is the governance token that is used by holders to maintain the system and manage DAI.

![](https://lh6.googleusercontent.com/bdJFSZefZMeFODLVOXcerR2df0cryZosY0XUEXMKZ6IWEoFtURTYAjZXVSecfHVuIv6qL9nKAkFIGS6UgGgXGOPkaXd07xbmVlD680vv5Euy-6oPvLHLi4y-s4hWp2B4vIlpT7St5Tuz4TsLvgA)

### 2. Category

AMM, DEX, Lending and Borrowing.

### 3. Does it have TVL?

Yes, the total TVL is $15.81b as of 27 March 2022 \[2]. The current TVL can be retrieved [here](https://defillama.com/protocol/makerdao).

### 4. What are its...?

As of 27 March 2022

* Liabilities: - $ [9.76 bln](https://daistats.com/#/collateral) \[3].
* Reserves: - NA
* Assets: -  NA
* Treasury: - NA
* Market Cap: - MKR [$1.87 bln](https://www.coingecko.com/en/coins/maker), DAI [$9.08 bln](https://www.coingecko.com/en/coins/dai) \[4]
* Ratio of Reserves to TVL (deposits only; unleveraged): - NA
* Ratio of Treasury to TVL (deposits only; unleveraged): - NA
* Ratio of native Market Cap to TVL (deposits only; unleveraged): - 0.1198
* Are they double-counting leverage?  NO

### **5. Further details on the Token?**

#### Markets where it’s available?

The purchase of DAI tokens is available on numerous online platforms. These include Decentralized Finance (DeFi) token swap protocols:&#x20;

* Uniswap&#x20;
* Sushiswap&#x20;

And traditional cryptocurrency exchanges:&#x20;

* Coinbase Pro&#x20;
* Binance&#x20;
* OKEx&#x20;
* HitBTC&#x20;

List of all markets can be found [here](https://coinmarketcap.com/currencies/multi-collateral-dai/markets/) \[5].

#### Liquidity

* Circulating Supply -  Total amount of tokens in circulation  977,631.04 MKR \[4]
* Total Supply ****            - on-chain supply minus burned tokens 977,631 \[4].
* Max Supply            - theoretical maximum as coded 1,005,577 \[4].
* The DAI supply is based on the current Maker Vaults and how many DAI are currently minted upon them.

### **6. What chain is it on?**

**Multichain**

MakerDAO was initially built on the **Ethereum** chain but now supports \[6].

* Avalanche
* xDAI
* BSC&#x20;
* Fantom&#x20;
* Klaytn
* Polygon

### **7. Could it be exploited?**

No yet, but MakerDAO has announced that it will begin offering a maximum of $10 million bounty to white hat hackers and cybersecurity specialists who point out legitimate security threats in its smart contracts \[7].

### **8. What assets does it support?**&#x20;

The [following assets](https://oasis.app/borrow) are supported by MakerDAO \[8]:

1. **ETH**
2. **BTC**
3. **UNI**
4. **YFI**
5. **UNI LP**
6. **Curve LP**
7. **LINK**
8. **MANA**
9. **MATIC**
10. **GUSD**

### **9.** How does it combine the risks of those assets?

The Maker Protocol faces risks associated with collateral risk, monetary policy, and operational risks \[9]. **** Risk levers such as the Stability Fee, DAI Savings Rate, and the collateral onboarding process can be used to influence both Vault and DAI holder behavior in order to facilitate a market equilibrium at $1. Because the supply and demand for DAI fluctuate based on a variety of market factors, creating an accurate model requires a sound understanding of economics, statistics, market psychology, and more \[10].

### **10. Does it wrap and distribute assets?**

No, it does not. It creates collateralized debt positions (CDP) to maintain the peg of DAI to the USD \[17].

### **11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?**

In order to borrow borrower / mint new DAI, the user looks up funds in the CDP smart contract with a specific Liquidation Ratio, say 150%. Thus you will need to provide $150 worth of ETH to borrow $100 DAI. As the collateral falls below the 150% rate, the user will get liquidated if he is not able to repay its DAI debt \[17].

In the current system, in each call to the liquidation function (Cat.bite) transfers a fixed amount of debt (the dunk) from the affected Vault, along with a proportional amount of the Vault's collateral to the protocol. For example, if 50% of a Vault's debt is taken by the protocol, then half of its collateral is taken as well. If the Vault's debt is less than the dunk, then all debt and collateral is taken. In version 2.0, all debt is taken when the liquidation function (Dog.bark) is called, and no analogue of the dunk parameter exists. The reasoning behind this change is that because the new auctions allow partial purchases of collateral, the liquidity available to a participant no longer limits their ability to participate in auctions, so instead the total number of auctions should be minimized. Just to emphasize, there is no longer a minimum DAI liquidity requirement for the sale of collateral on a per-participant basis \[11].

### **12. What are the dependencies of the protocol? How does risk bubble up?**

As DAI tries to maintain a 1:1 peg to the USD, the value is ultimately determined by the ability of the protocol to liquidate under-collateralized vaults, especially in market periods with high volatility of the underlying collateral assets.

A dai.js plugin for interacting with the MKR governance system. This plugin makes it easy to integrate DAI governance into frontend applications such as the Maker governance dashboard. You can use it to vote, cast proposals, query the voting contract, create a vote proxy, and much more \[12].

### **13. Does it have a governance token?**

The MKR token—the governance token of the Maker Protocol—allows those who hold it to vote on changes to the Maker Protocol. Note that anyone, not only MKR holders, can submit proposals for an MKR vote \[13]. MKR is an ERC-20 token that is native to the Maker Protocol.

### **14.** How decentralized is it?

The Maker Protocol is managed by people around the world who hold its governance token, MKR. Through a system of scientific governance involving Executive Voting and Governance Polling, MKR holders govern the Protocol and the financial risks of DAI to ensure its stability, transparency, and efficiency. One MKR token locked in a voting contract \[13]. MakerDAO launched with 1,000,000 MKR tokens at its inception. The tokens are created and destroyed under different circumstances.

### 15. Additional Information

* **VAR  -** VAR can be computed using the total collateral deposited and total loaned amount.
* **LCR -**  To be provided
* **Sharpe Ratio -** Price of DAI token can be used to compute sharpe ratio.
* **Annual percentage Ratio(APR)  -** Annual percentage rate (APR) refers to the yearly interest generated by a sum that's charged to borrowers or paid to investors. APR is expressed as a percentage that represents the actual yearly cost of funds over the term of a loan or income earned on an investment \[14].

### 16. How is this protocol exposed to the different layers in DeFi:

#### What layers are upstream (built on top of the protocol)? Are other protocols that use it as a source of data/pricing oracle, or put funds into it?

Over 400 apps and services have integrated DAI, including wallets, DeFi platforms, games and more \[15]. Thus any manipulation of DAI might bubble up to a lot of different applications that use DAI as collateral for their protocols.

#### What layers are downstream (protocols/assets built on or put into the platform)? For example, yield farms are built on top of lending protocols

The reference prices for the Maker system are provided via the so-called ["Medianizer" oracle](https://developer.makerdao.com/feeds/) \[18]. Thus, any manipulation of this oracle price feed will directly impact the DAI stability and its 1:1 peg to the USD.

### 17. Smart Contract information&#x20;

All the relevant smart contracts can be found [here](https://daistats.com/#/addresses) \[16].

## References

1. MakerDAO, https://makerdao.world/en/learn/governance/mkr-token&#x20;
2. Defillama, https://defillama.com/protocol/makerdao&#x20;
3. DaiStats, https://daistats.com/#/collateral&#x20;
4. Coingecko, https://www.coingecko.com/en/coins/maker & https://www.coingecko.com/en/coins/dai
5. Coinmarketcap, https://coinmarketcap.com/currencies/multi-collateral-dai/markets/&#x20;
6. MakerDAO, https://forum.makerdao.com/t/a-look-at-dai-on-different-chains/9231&#x20;
7. Cointelegraph, https://cointelegraph.com/news/makerdao-launches-biggest-ever-bug-bounty-with-10m-reward&#x20;
8. MakerDAO, https://oasis.app/borrow&#x20;
9. MakerDAO, https://makerdao.world/en/learn/collateral-and-risk/types-of-risk/&#x20;
10. MakerDAO, https://makerdao.world/en/learn/vaults/risk&#x20;
11. MakerDAO, https://docs.makerdao.com/smart-contract-modules/dog-and-clipper-detailed-documentation&#x20;
12. NpmJS, https://www.npmjs.com/package/@makerdao/dai-plugin-governance&#x20;
13. MakerDAO, https://makerdao.world/en/learn/governance/mkr-token&#x20;
14. Investopedia, https://www.investopedia.com/terms/a/apr.asp&#x20;
15. MakerDAO, https://makerdao.com/en/ecosystem/&#x20;
16. DaiStats, https://daistats.com/#/addresses
17. A Guide to MakerDao and Dai, https://academy.binance.com/en/articles/a-guide-to-makerdao-and-dai
18. MakerDAO feeds, https://developer.makerdao.com/feeds/

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 $CMK (internal) | Original version |

&#x20;

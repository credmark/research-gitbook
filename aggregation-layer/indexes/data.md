---
description: The Data Economy Index
---

# DATA

## What is it?&#x20;

Token

$DATA is a token that represents a share in The Data Economy Index, a fully collateralized onchain index maintained on the Ethereum mainnet using Set Protocol.

Users can mint DATA by supplying the underlying assets in the index to the index contract to be managed for them. In return they get back DATA to represent their share of the index holdings.&#x20;

Anyone with DATA can send tokens back to the index and receive back the underlying tokens. This is how TVL is added to the index and also how arbitrageurs maintain the NAV pricing of DATA on the market.

## Category:&#x20;

Index

The Data Economy Index is a market cap weighted index managed by [Indexcoop](https://docs.credmark.com/credmark-risk-library/defi-protocol-taxonomy/indexes/index-protocols/indexcoop).

\
It tracks an ecosystem of Web3 data-based products and services such as Chainlink, Filecoin, The Graph, and ENS.&#x20;

Whereas DeFi is disrupting traditional banking and financial services, the Data Economy is disrupting the data monopolies built in Big Tech over the past 20 years.&#x20;

A 5’ overview including the full constituent list can be read [here](https://blog.titansofdata.org/investing-in-the-future-of-the-data-economy/).

## Does it have TVL?&#x20;

On Feb 6st 2022 DATA had a TVL of $1,880,000

TVL is measured as the NAV of the underlying assets held within the DATA index contract that are redeemable by token holders. The market cap displayed on TokenSets.com, a frontend for Set Protocol, also tracks the NAV.&#x20;

Other sources for the DATA market cap (such as CoinGecko) track the market price of DATA on exchanges, not the NAV, although exchange prices historically track the NAV to within a few percentage points.

TVL calc&#x20;

I = # underlying tokens&#x20;

Summation = Pricei \* Tokens per DATA \* Total DATA Units&#x20;

I = 0

## Protocol and pool level information

Assets Value of underlying tokens held in the index&#x20;

Liabilities Value of outstanding DATA tokens&#x20;

Reserves: N/A&#x20;

Treasury: N/A&#x20;

Market Cap: $1,880,000 (Feb 6th 2022)&#x20;

Ratio of Reserves to TVL: N/A&#x20;

Ratio of Treasury to TVL: N/A&#x20;

Ratio of native Market cap to TVL: N/A&#x20;

Are they double counting leverage? N/A

## Further details on the Token?&#x20;

### Markets where it’s available&#x20;

Sushi mainnet - https://analytics.sushi.com/pairs/0x208226200b45b82212b814f49efa643980a7bdd1 Sushi&#x20;

polygon - https://analytics-polygon.sushi.com/pairs/0xf2c9650fd759f93e59d2ae8f42a97c0600150f0e

Index Coop mainnet + polygon https://app.indexcoop.com/data

TokenSets mainnet https://www.tokensets.com/portfolio/data

### Liquidity

Circulating Supply 29,052&#x20;

Total Supply 29,052&#x20;

Max Supply: Unlimited mint/redeem

## **What Chains is it on?**

Ethereum mainnet is the only place to access DATA’s mint/redeem functionality which allows you to deposit or withdraw tokens to be managed by the index contract.&#x20;

The DATA tokens represent shares of underlying tokens so they can be bridged to any chain while the assets themselves remain on mainnet.

## Could it be exploited?&#x20;

**Is it Cross Chain?** No but ca.. 25% of the value is backed by renFIL representing Filecoin tokens bridged with the Filecoin chain Broadcasts Value Instantaneous&#x20;

**Reentrancy risks?** No&#x20;

**Using Price Oracles?** No

It could in theory be exploited if the Data Economy Index manager (Index Coop) executes a rebalance into a malicious token that would allow user funds to be siphoned to them through the AMM pool.

## **What assets does it support?**

Set Protocol, the underlying tech, can support any non-rebase ERC20 token.&#x20;

The [Data Economy Index inclusion criteria](https://blog.titansofdata.org/investing-in-the-future-of-the-data-economy/) dictate which tokens qualify as “Web3 data protocols”.

## How does it combine the risks of those assets?&#x20;

**Average:** NA&#x20;

**IL Curve:** NA&#x20;

**Borrow/Lend Exposure:** NA

## Does it wrap and distribute assets? (e.g. Aave, Sushi)&#x20;

No.&#x20;

Minting DATA can be seen as wrapping underlying tokens and getting DATA returned back.&#x20;

Also, Indexcoop executes the redistribution of assets internally to rebalance weights but this isn’t within the meaning of the question (we think).

## What are the conditions for the wrapped assets to be liquidated?

N/A

## What are the dependencies of the protocol to other protocols / tokens? How does risk bubble up?&#x20;

Set Protocol.&#x20;

Indexcoop relies on AMMs to rebalance components.That’s not inherent however to the functionality of the DATA token itself, only to its ongoing viability as an investment that tracks the underlying market constituents.

## Does it have a governance token?

INDEX tokens (from Indexcoop) control the DATA token and onchain product (i.e. the technical infrastructure, technologies and metagovernance rights of the underlying tokens).&#x20;

If DATA were going to start yield farming assets held in the Data Economy Index (not currently enabled), Indexcoop and INDEX holders would firstly decide whether that should be allowed and then which farming strategies would be used.

The methodologist that created and maintains the Data Economy Index itself only has control over which tokens get added or removed and their weights in the Index and is on the multi-sig that executes the rebalancing.

## How decentralized is?

https://dune.xyz/thomashepner/DATA

**The Token:** \~700 holders on mainnet and Polygon. 1 holder controls \~69% of liquidity and 22% of total supply. This holder is Wintermute, a professional market maker that has invested in Index Coop.&#x20;

**Decision Making:**  All decisions related to managing DATA go through Index Coop’s governance process. For example, here you can see the proposal to launch DATA.&#x20;

**Profits:**  Fees **** associated with DATA are split between Index Coop and the methodologist to distribute however they want. Currently both keep their fees without distributing to any token holders.

## Additional Information&#x20;

**VAR**:  Since DATA is a simple index product, we don’t think this metric is relevant.&#x20;

**LCR**:  Since DATA is a simple index product, we don’t think this metric is relevant.&#x20;

**Are there any other metrics that might be useful?** Like Sharpe Ratio? Correlation to ETH/BTC? We don’t currently calculate any other such metrics.

## How is this exposed to layers in DeFi?

**What layers are upstream (built on top of the protocol)?**

Nothing is built on top. DATA is accepted as collateral on some Rari Fuse pools and leveraged farming protocols.

**What layers are downstream (protocols/assets built on or put into the platform)?**&#x20;

Set Protocol infrastructure, Index Coop management contracts, DEXs

## Smart Contract information

**Protocol smart contract address**: NA

**Token smart contract address** https://etherscan.io/token/0x33d63ba1e57e54779f7ddaeaa7109349344cf5f1 Are there any other relevant smart contracts?

**Are there any other relevant smart contracts?** No

## References

https://blog.titansofdata.org/investing-in-the-future-of-the-data-economy/&#x20;

DATA Token smart contract address**:** https://etherscan.io/token/0x33d63ba1e57e54779f7ddaeaa7109349344cf5f1&#x20;

[https://gov.indexcoop.com/t/iip-59-final-data-economy-index-data/2310](https://gov.indexcoop.com/t/iip-59-final-data-economy-index-data/2310)

[https://dune.xyz/thomashepner/DATA](https://dune.xyz/thomashepner/DATA)

## Contributors

This material was written by Kiba Gateaux, a core contributor to Titans of Data. Titans of Data is the Methodologist of the DATA Index. BobZedF contributed as Editor.



| Twitter Handle | ETH Address | Reward | Contribution     |
| -------------- | ----------- | ------ | ---------------- |
| @KibaGateaux   |             |        | Original version |
| @BobZedF       |             |        | Editor           |

# Goldfinch Finance

Goldfinch is a decentralized credit protocol with a mission to expand access to capital and foster financial inclusion. The protocol makes crypto loans without crypto collateral. This is the missing piece that finally unlocks crypto lending for most people in the world. The Goldfinch community makes loans to companies around the world, starting with emerging markets \[1] \[7].



![](<../../.gitbook/assets/image (2).png>)

### 1. Is It a Protocol or Token?

Both Protocol and Token.

It has a token named GFI. The protocol is governed by the community via the Goldfinch Council and the community can actively participate in governance at gov.goldfinch.finance.



### 2. Category ****&#x20;

Goldfinch is a decentralised protocol that allows for crypto borrowing without crypto collateral \[2].

The protocol works by extending credit lines to lending businesses. These businesses use their credit lines to draw down stablecoins from the pool (USDC), and then they exchange it for fiat and deploy it on the ground in their local markets. In this way, the protocol provides the utility of crypto — specifically, its global access to capital — while leaving the actual loan origination and servicing to the businesses best equipped to handle it.

On the capital provider side, crypto holders can supply into different pools to earn yield. As the lending businesses make their interest payments back to the protocol, they’re immediately disbursed to all capital providers \[1].

\


The Goldfinch protocol has four core participants: Borrowers, Backers, Liquidity Providers, and Auditors.&#x20;

Borrowers are participants who seek financing, and they propose Borrower Pools for the Backers to assess. Borrower Pools contain the terms a Borrower seeks, like the interest rate and repayment schedule.&#x20;

Backers assess the Borrower Pools and decide whether to supply first-loss capital. After Backers supply capital, Borrowers can borrow and repay through the Borrower Pool \[2].&#x20;

Liquidity Providers supply capital to the Senior Pool in order to earn passive yield. The Senior Pool uses the Leverage Model to automatically allocate capital to the Borrower Pools, based on how many Backers are participating in them. When the Senior Pool allocates capital, a portion of its interest is reallocated to the Backers. This increases the Backers’ effective yield, which incentives them to both provide the higher-risk first-loss capital and do the work of assessing Borrower Pools.&#x20;

Lastly, Auditors vote to approve Borrowers, which is required before they can borrow. Auditors are randomly selected by the protocol, and they provide a human-level check to guard against fraudulent activity \[2].



### 3. Does it have TVL? **** -&#x20;

Yes, total TVL is $111.97M as of 4th April 2022. All of it is in Ethereum chain \[3].

How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?&#x20;

Their Frontend, Dune, DefiPulse - To be provided.

DefiLlama - It counts liquidity that is in both the Senior Pool as well as that from Backers in all the TranchedPools \[3].



### 4. Provide the following information at a protocol and pool level where appropriate:

&#x20;   As of 21 Jan 2022

* Assets\
  Not  applicable
* Liabilities\
  Not applicable
* Reserves\
  Not available
* Treasury&#x20;
*   Market Cap

    $17,142,355 \[4]
* Ratio of Reserves to TVL (deposits only; unleveraged)\
  Not available
* Ratio of Treasury to TVL (deposits only; unleveraged)\
  To be Provided
* Ratio of native Market Cap to TVL (deposits only; unleveraged)\
  To be Provided
* Are they double-counting leverage? - NO

### 5. Further details on the Token?



* Markets where it’s available?&#x20;
  * List of markets can be found here \[5].
* Liquidity:
  * Circulating Supply -  the total amount of tokens in circulation  5,072,242.00 GFI \[4].
  * Total Supply - on-chain supply minus burned tokens 114,285,714 \[4].
  * Max Supply - theoretical maximum as coded 114,285,714 \[4].

### 6. What chain is it on? - MultiChain

It is on Ethereum Chain only \[1].

\


### 7.  Could it be exploited?

So far, it has neither been exploited, nor any major vulnerabilities have been found according to the audits \[6].



### 8. What assets does it support?&#x20;

To be Provided\


### 9. How does it combine the risks of those assets?

According to investorsoberserver.com, it is of medium risk rank. This means the price of the cryptocurrency can move pretty quickly, but it is relatively in proportion to the value of the Goldfinch being traded. A medium rank means the price can still move around a lot, but the price is less likely to be manipulated and big moves will likely mean increased interest in trading Goldfinch \[10].

### &#x20;10. Does it wrap and distribute assets?

No it does not wrap assets

### 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

&#x20;Borrowers are participants who seek financing from the protocol. They propose terms to Backers to supply capital to their Borrower Pools. A Borrower Pool is the smart contract through which Borrowers borrow and repay capital. Any Borrower can create a Borrower Pool and define the terms they want:&#x20;

* Interest Rate: Fixed interest rate APR, e.g. 15%.&#x20;
* Limit: Total capital that can be borrowed, e.g. $1M.&#x20;
* Payment Period: Frequency of interest payments, e.g. every 30 days.
* Term: When the full principal is due, e.g. 365 days.
* Late Fee: Additional interest owed when payments are late, e.g. 5%.&#x20;

Creating a Borrower Pool is like proposing a “term sheet” to Backers. It does not guarantee the terms will be accepted, since Borrowers then need to convince Backers to supply junior tranche (first-loss) capital. The amount Borrowers can borrow is based on how much Backers supply, combined with the amount the Senior Pool allocates based on the Leverage Model.

In order to create a Borrower Pool, the Borrower must also stake an amount of GFI equal to double the cost of an Auditor approval, which is a fixed rate set by the protocol. This helps guard against spam, signal to Backers that the Borrower is serious, and provide GFI to pay for the first Auditor approval. The first half of the staked GFI is used for the first Auditor approval. The Borrower can redeem their remaining staked GFI when they have fully repaid their borrowed balance.&#x20;

After borrowing, Borrowers make repayments to the Borrower Pool according to its interest rate and payment period. When they pay more than the interest owed, the remainder is applied to the principal balance \[2].



### 12. What are the dependencies of the protocol? How does risk bubble up?

Goldfinch Finance does not have any dependencies on any third party apps or APIs.

### 13. Does it have a governance token&#x20;

&#x20;        Yes, its name is GFI. Governance is managed by a community DAO and has the ability to perform maintenance functions and parameter adjustments via decentralised governance votes, including:&#x20;

* Upgrading contracts&#x20;
* Changing protocol configurations and parameters&#x20;
* Selecting Unique Entity Check providers&#x20;
* Setting the rewards and distribution of GFI&#x20;
* Pausing protocol activity in the event of an emergency \[2].

### &#x20;14: How decentralised is&#x20;

&#x20;Anyone can participate in governance by making proposals, discussing them, and participating in Snapshot votes.

**Governance Forum**

The Goldfinch community governance portal is located here \[8]. This is a venue for the community to make and discuss proposals. More details on the proposal process are at the governance portal here.&#x20;

**Snapshot Votes**

Snapshot votes take place at here. You can use your GFI balance to vote, and the results are calculated according to Quadratic Voting. To ensure sybil resistance with quadratic voting, participants need a Unique Identity NFT (UID) in order to vote. Unique Identity (UID) is a non-transferrable NFT representing Know-Your-Customer verification on chain. It is the first NFT for identity. It follows ERC-1155 standards, and is freely usable by any other protocol. No personally identifiable data is stored on-chain \[1].&#x20;

The Goldfinch Council has been set up to execute limited types of on-chain transactions based on the community Snapshot votes. The Goldfinch Council is a 6-of-10 multisite with 10 members who represent all stakeholders of the protocol \[1]. List of these members can be found here \[9].



### 15. Additional Information

* VAR  - Not applicable
* LCR - Not applicable
* Are there any other metrics that might be useful?Like Sharpe Ratio

Annual percentage yield(APY) - APY is an important metric that any liquidity provider or investor should follow in Uniswap. APY provides a real rate of return earned on a liquidity pool into account the effect of compounding interest.High-quality borrowers provide expected 10-14% APY from real-world activity uncorrelated with crypto \[11].\


### 16. How is this exposed to layers in Defi:

* What layers are upstream (built on top of the protocol)? Are there other protocols that use it as a source of data/pricing oracle, or put funds into it?

There are businesses that partner with goldfinch finance. They can be found here \[11].

* What layers are downstream (protocols/assets built on or put into the platform). For example, yield farms are built on top of lending protocols

Goldfinch Finance is not sourcing data from anywhere.\


### 17. Smart Contract information

* List the protocol´s smart contract address&#x20;

&#x20;    Goldfinch protocol address : To be Provided

* List the Token´s smart contract address

&#x20;    GFI token tracker address: 0xdab396cCF3d84Cf2D07C4454e10C8A6F5b008D2b \[12].

* Are there any other relevant smart contracts?  No

\


**References:**&#x20;

1. Docs.goldfinch, [https://docs.goldfinch.finance/goldfinch/](https://docs.goldfinch.finance/goldfinch/)
2. Goldfinch.finance, [https://goldfinch.finance/goldfinch\_whitepaper.pdf](https://goldfinch.finance/goldfinch\_whitepaper.pdf)
3. Defillama, [https://defillama.com/protocol/goldfinch](https://defillama.com/protocol/goldfinch)
4. Coinmarketcap, [https://coinmarketcap.com/currencies/goldfinch-protocol/](https://coinmarketcap.com/currencies/goldfinch-protocol/)
5. Coinmarketcap, [https://coinmarketcap.com/currencies/goldfinch-protocol/markets/](https://coinmarketcap.com/currencies/goldfinch-protocol/markets/)
6. Github, [https://github.com/goldfinch-eng/goldfinch-contracts/blob/main/v2.0/Certik-Goldfinch-Audit-Report-2021-8-26.pdf](https://github.com/goldfinch-eng/goldfinch-contracts/blob/main/v2.0/Certik-Goldfinch-Audit-Report-2021-8-26.pdf)
7. Medium, [https://medium.com/goldfinch-fi/introducing-goldfinch-crypto-loans-without-collateral-fc0cad9d13e](https://medium.com/goldfinch-fi/introducing-goldfinch-crypto-loans-without-collateral-fc0cad9d13e)
8. Gov.goldfinch, [https://gov.goldfinch.finance/](https://gov.goldfinch.finance).
9. Docs.goldfinch, [https://docs.goldfinch.finance/goldfinch/governance](https://docs.goldfinch.finance/goldfinch/governance)
10. Investorsobserver, [https://www.investorsobserver.com/crypto/13967/gfi](https://www.investorsobserver.com/crypto/13967/gfi)
11. Goldfinch.finance, [https://goldfinch.finance/](https://goldfinch.finance)
12. Etherscan, [https://etherscan.io/token/0xdab396ccf3d84cf2d07c4454e10c8a6f5b008d2b](https://etherscan.io/token/0xdab396ccf3d84cf2d07c4454e10c8a6f5b008d2b)



Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| Deadsec        | 0x1A2E1d4553d33c080746A056AA3F832823fADB51 | 0 $CMK (internal) | Original version |

\



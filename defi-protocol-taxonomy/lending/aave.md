---
description: By Rahul Kanojia and Shivam Garg, 14 January 2022
---

# Aave

Aave is an open-source and non-custodial liquidity protocol for earning interest on deposits and borrowing assets.

## 1. Is It a Protocol or Token? - Both Protocol and Token

Aave is a decentralized non-custodial liquidity protocol where users can participate as depositors or borrowers \[1]. Depositors provide liquidity to the market to earn a passive income, while borrowers are able to borrow from the market by using their cryptocurrency as collateral. Aave also has a token by a similar name, AAVE which is used to power governance and to vote changes on future developments of the protocol.

## 2. Category - Lender

Aave is a borrowing and lending platform that offers both Collateralized and Uncollateralized Loans \[2]. Aave offers collateralized loans on multiple blockchains such as ethereum, polygon and avalanche and was the first protocol to introduce uncollateralized loans in the history of DeFi through Flash Loans which let users borrow significant amounts of money (millions and bln.s) only to be repaid within a single transaction block.

## 3. Does it have TVL?

Yes, $13.18 bln. as of 14 January 2022 \[4]

### How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?

As of 2nd December’ 2021 Aave protocol’s TVL stands at approx. $27.1 bln., distributed across multiple chains as per below:

Ethereum Chain - $16.6 bln.

Polygon Chain - $4.2 bln.

Avalanche Chain - $6.6 bln.

## 4. What are it’s

As of 14 January 2022:

* Liabilities $13.57 bln.&#x20;
* Assets $5.86 bln.&#x20;
* Reserves $3 mln. \[28]&#x20;
* Treasury $28.18 mln. (Etherium Reserve Factor) $433.05 mln. (Ecosystem Reserve balance) \[29]&#x20;
* Ratio of Reserves to TVL (deposits only; unleveraged) 2.276176024279211e-4&#x20;
* Ratio of Treasury to TVL (deposits only; unleveraged) 0.0021380880121396&#x20;
* Ratio of native Market Cap to TVL (deposits only; unleveraged) 0.2134 \[30]&#x20;
* Are they double-counting leverage? No

## 5. Does the protocol have its own Token?

Yes, Aave protocol has its native token of a similar name, AAVE.

## 6. What chain is it on?

Multichain. AAVE token was initially built on ethereum chain but now has been deployed on Binance Smart Chain, Heco, xDAI, Polygon, Avalanche, Fantom, and Sora chains to cater to large users \[5].

## 7. Could it be exploited?

Yes

### Is it Cross Chain?

Yes, via a bridge, but unilateral \[8]. Aave offers services on multiple blockchains such as ethereum, polygon, and avalanche. It can also be referred to as cross-chain in the sense that debt and liabilities from ethereum chain to other chains. (through its own governance cross-chain bridge.) The bridged tokens are received in a wrapped form \[6].

There are currently two downsides to this bridge:

1. This process is only one way. (You cannot move debt and liabilities from other chains to the Ethereum chain.)
2. It only supports Polygon and Arbitrum chains.

There is also one other bridge in existence ( instadapp-labs’ bridge) but offers no improvement over Aave’s bridge i.e. ability to cross-chain transfer \[7].

Broadcasts Value, as of 14 January 2022 \[31]

* TWAP 0.0014
* Instantaneous 0.001941

### Reentrancy risks?

Aave’s smart contract earlier contained a reentrancy risk which was pointed out in this audit by OpenZeppelin \[12] and was later fixed by Aave. This fix was also confirmed by yet another audit by Consensys \[13].

### Using Price Oracles?&#x20;

Aave uses the ChainLink price oracle system. At the same time, as backup, the Aave team runs a centralized oracle based on deriving a median from multiple price sources to be used only in the case of a Chainlink aggregator submitting completely wrong prices \[10].

## 8. What assets does it support?

Currently, Aave supports 31 assets, including ETH, DAI, sUSD, Gemini Dollar, USDC, TUSD, USDP, USDT, Balancer, Chainlink, Maker, Rai, Uniswap, WBTC, SUSHI, Yearn Finance, BUSD, FUSD, Frax, AAVE, etc.

## 9. How does it combine the risks of those assets?

### Borrow/Lend Exposure

Aave’s interest rate strategy is calibrated to manage liquidity risk and optimize utilization. The borrow interest rate comes from the Utilization Rate U. U is an indicator of the availability of capital in the pool.

The interest rate model is used to manage liquidity risk through user incentivizes to support liquidity:

* When capital is available: low-interest rates to encourage loans.
* When capital is scarce: high-interest rates to encourage repayments of loans and additional deposits.

The interest rate models are derived from the formula given in the Whitepaper\[15].

## 10. Does it wrap and distribute assets?

Yes, Aave wraps and distributes assets into interest-bearing tokens (aTokens for short) to lenders. The aTokens are pegged 1:1 to the value of the underlying asset that is deposited in the Aave protocol. aTokens, such as aDai or aETH, can be freely stored, transferred, and traded.

## 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

Back to the original portfolio. aTokens are minted upon deposit and burned when redeemed. Upon liquidating aToken, the owner will get the underlying token (Dai in case of aDai) and the redeemed aToken will be burned \[9].

In case of the maximum amount borrowed against collateral with specific LTV\[], If the price of collateralized moves up and makes the borrowed amount more than LTV value, the collateralized assets will liquidate and make up for the exceeded amount and the remaining amount will be adjusted to the portfolio \[10].

## 12. What are the dependencies of the protocol? How does risk bubble up?

Chainlink, Price Oracles

## 13. Does it have a governance token?

Aave also has a token by a similar name, AAVE which is used to power governance and to vote changes on future developments of the protocol.AAVE token can also provide users discounted token fees on the platform. Traders can also speculate on the price of AAVE, hoping to buy low and sell at a higher price later \[22].

## 14. How decentralized is?

### The Token

Aave token is currently deployed on 8 chains consisting of Ethereum, Binance, Fantom, Polygon, Avalanche, Sora, xDai, Heco chains. It was audited by Certik. Current total holders are 111,361 and 50% of supply is present with the top 5 Holders. (30% of total supply is staked and reserved within Aave and 9.5% is with Aave Protocol)

### Decision Making

Aave’s governance power rests with the community where Aave token holders (stacked and unstacked) can not only vote on proposals introduced by Aave platform but will also be able to create proposals themselves. Aave holders can also delegate their proposal power to another actor, a ‘protocol politician’ while retaining their voting rights. Profits Aave is a Switzerland-based for-profit company that acts as a bank(lender) in the DeFi ecosystem. Apart from distributing interest to depositors, Aave takes some part of interest for facilitating its services.

Profits from uncollateralized loans (Flash Loans) are 100% deposited to the Aave organization.

## 15. How is this exposed to layers in DeFi:

### What layers are upstream (built on top of the protocol)?

Are there other protocols that use it as a source of data/pricing oracle, or put funds into it? Since Aave is a lending protocol, no layers are currently built on top of Aave and currently, no other known protocols use Aave as a source of data pricing, while Aave itself relies on Chain Link Data Oracle for pricing. While a substantial number of smart contracts are known to use Aave for the purpose of taking Flash Loans.\[25]

### What layers are downstream (protocols/assets built on or put into the platform)? For example, yield farms are built on top of lending protocols.

Aave recently announced its plans to scale its DeFi platform on Layer 2 networks beyond the Ethereum Blockchain but currently only incorporates Polygon network. It foresees building on other chains in the future. Since Aave is a lending pool and not a p2p lending platform, yields are given to depositors whether or not their assets are loaned out to borrowers so it also behaves as a yield farm.\[24]

## References

1. AAVE, https://aave.com/
2. AAVE, https://docs.aave.com/portal/
3. Medium, https://medium.datadriveninvestor.com/defi-coin-aave-invest-in-decentralized-lending-b595fb2a7aaa&#x20;
4. Defilama, https://defillama.com/protocol/aave&#x20;
5. Defipulse, https://defipulse.com/aave&#x20;
6. Binance, https://academy.binance.com/en/articles/what-is-aave&#x20;
7. Coinmarketcap, https://coinmarketcap.com/currencies/aave/&#x20;
8. Github, https://github.com/aave/governance-crosschain-bridges&#x20;
9. Instadapp, https://intercom.help/instadapp-labs/en/articles/5164706-migrating-aave-positions-between-ethereum-and-polygon-using-the-migration-bridge&#x20;
10. Chainlinkecosystem, https://www.chainlinkecosystem.com/ecosystem/aave/&#x20;
11. Medium, https://smartcontentpublication.medium.com/twap-oracles-vs-chainlink-price-feeds-a-comparative-analysis-8155a3483cbd&#x20;
12. Openzeppelin, https://blog.openzeppelin.com/aave-protocol-audit&#x20;
13. Consensys, https://consensys.net/diligence/audits/2020/09/aave-protocol-v2/&#x20;
14. AAVE, https://github.com/aave/aave-protocol/blob/master/docs/Aave\_Protocol\_Whitepaper\_v1\_0.pdf&#x20;
15. AAVE, https://github.com/aave/protocol-v2/blob/master/aave-v2-whitepaper.pdf&#x20;
16. WisdomTree, https://www.wisdomtree.com/blog/2021-08-24/introduction-to-ethereums-dapps-deep-dive-into-aave&#x20;
17. AAVE, https://medium.com/aave/understanding-the-risks-of-aave-43334dbfc6d0#:\~:text=Still%2C%20full%20utilization%20remains%20very,%2C%206.5%25%20of%20the%20time.&#x20;
18. Certik, https://www.certik.com/projects/aave&#x20;
19. Medium, https://medium.com/aave/aave-protocol-governance-v2-has-been-activated-af4a4b228885&#x20;
20. Kraken, https://www.kraken.com/en-us/learn/what-is-aave-lend&#x20;
21. Cryptobriefing, https://cryptobriefing.com/aave-will-build-matics-scalable-layer-2-platform/&#x20;
22. Decrypt, https://decrypt.co/resources/what-is-aave-inside-the-defi-lending-protocol&#x20;
23. Arxiv, https://arxiv.org/pdf/2107.14678.pdf
24. Medium, https://medium.com/aave/understanding-the-risks-of-aave-43334dbfc6d0
25. Aave, https://docs.aave.com/risk/asset-risk/risks-per-asset
26. Medium, https://medium.com/gauntlet-networks/aave-market-risk-assessment-becef6d6422f
27. Aave, https://docs.aave.com/risk/asset-risk/methodology
28. Aave, https://docs.aave.com/aavenomics/incentives-policy-and-aave-reserve
29. Dune, https://dune.xyz/llama/Aave-Treasury-Finances-by-Llama
30. Coinmarketcap, https://coinmarketcap.com/currencies/aave/markets/
31. Bitmex, https://www.bitmex.com/app/index/.AAVEUSDTPI8H

---
description: By Rahul Kanojia and Shivam Garg, 17 January 2022
---

# Curve Finance

The easiest way to understand Curve is to see it as an exchange. Its main goal is to let users and other decentralized protocols exchange stablecoins (DAI to USDC for example) through it with low fees and low slippage. Unlike exchanges out there that match a buyer and a seller, the behaviour of Curve is different, it uses liquidity pools like Uniswap. To achieve this, Curve needs liquidity (tokens) which is rewarded by those who provide it \[1].

## 1. Is It a Protocol or Token?

Both Protocol as well as Token.

The curve is a popular automated market maker (AMM) platform that offers a highly efficient way to exchange tokens while maintaining low fees and low slippage by only accommodating liquidity pools made up of similarly behaving assets. While this approach results in lower fees for the liquidity providers who supply the pools with tokens, Curve incentivizes their participation by integrating with external Defi protocols and delivering rewards in the form of CRV tokens and interest \[2].

## 2. Category - AMM, DEX

## 3. Does it have TVL?

Yes, $23.27 bln. as of 17 January 2022 \[3].

The curve has the following distribution of TVL as of 17 January 2022 \[3]:

| Arbitrum   | $16.6 bln.   |
| ---------- | ------------ |
| Avalanche  | $1.05 bln.   |
| Fantom     | $6.6 bln.    |
| Harmony    | $29.06 mln.  |
| Polygon    | $335.34 mln. |
| xDAI       | $67.15 mln.  |
| Ethereum   | $20.87 bln.  |

## 4. What are its core metrics?

* Liabilities\
  $ 23,26 bln. \[4]
* Reserves\
  $154 mln. \[5]
* Assets\
  $ 21.67 bln. \[6]
* Treasury\
  Not available
* TVL\
  $14.41 bln. \[7]
* Ratio of Reserves to TVL (deposits only; unleveraged)\
  0.010687023
* Ratio of Treasury to TVL (deposits only; unleveraged)\
  Not available
* Ratio of native Market Cap to TVL (deposits only; unleveraged)\
  0.08 \[16]
* Are they double-counting leverage? - NO

## **5: Does the protocol have its own Token?**&#x20;

Yes, Curve protocol has its native token of a similar name, CRV.

The CRV token can be locked for various periods of time (up to 4 years) in order to vote on governance and claim protocol fees as a reward. The main purposes of the Curve DAO token are to incentivize liquidity providers on the Curve Finance platform as well as get as many users involved as possible in the governance of the protocol \[8].

## **6: What chain is it on?**

Curve exists across several chains, with several more planned.  Curve's primary chain will always be Ethereum, but other side chains have advantages including speed and cost

Sidechains \[3]:

1\.    Arbitrum

2\.    Ethereum  &#x20;

3\.    Avalanche

4\.    Fantom

5\.    Harmony

6\.    Polygon

7\.    xDAI

## &#x20;**7. It could be exploited: Yes**

There is a security concern where a well-capitalized actor or a flash loan enabled adversary can execute a large swap on Curve to temporarily distort the prices of the two stablecoins involved as compared to the wider market prices for those assets. A malicious user can then exploit this price distortion by taking a position on a Defi protocol that offers Curve LP (Liquidity Pool) tokens as a collateral option which also relies on Curve as their price oracle when conducting transactions. The straightforward solution to this issue is to avoid using Curve as a price oracle and to rely on a reliable price oracle that provides an accurate picture of the global market price of the asset in a Liquidity Pool.

An example of an attack is shown in \[9].

It is Cross-chain, the Curve token can be bridged across some chains but does not always have full functionality. Staking of $CRV for veCRV must be done on Ethereum. Rewards voting for cross-chain gauges occurs on Ethereum.

## **8: What assets does it support?**&#x20;

Curve currently supports trading for the following stablecoins: DAI, USDT, USDC, GUSD, TUSD, BUSD, UST, EURS, PAX, sUSD, USDN, USDP, RSV, LINK, USD. Additionally, you can trade ETH, LINK, and a handful of tokenized BTC assets like wBTC and renBTC.

## **9: How does it combine the risks of those assets?**

The curve is an AMM platform with many similarities to [Uniswap](https://www.gemini.com/cryptopedia/uniswap-decentralized-exchange-crypto-defi) and [Balancer](https://www.gemini.com/cryptopedia/balancer-crypto-automated-pools) but differentiates itself by only accommodating [liquidity pools](https://www.gemini.com/cryptopedia/glossary#liquidity-pool) made up of similarly behaving assets like [stablecoins](https://www.gemini.com/cryptopedia/glossary#stablecoin), or wrapped versions of like assets such as [wBTC](https://www.gemini.com/cryptopedia/glossary#wrapped-bitcoin-w-btc) and [tBTC](https://www.gemini.com/cryptopedia/glossary#t-btc). This approach allows Curve to use more efficient algorithms, feature the lowest levels of fees, slippage, and [impermanent loss](https://www.gemini.com/cryptopedia/decentralized-finance-impermanent-loss-defi) of any decentralized exchange (DEX) on Ethereum.

In order to minimize impermanent loss, most of the protocol’s liquidity pools are made up of similar assets.

## **10: Does it wrap and distribute assets?**

If you deposit a stable coin to one of the pools with lending, Curve will automatically wrap your token to a cToken (for Compound) or a yToken(for iEarn).&#x20;

## **11: What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?**

The option is simply back to the original, if you have already previously wrapped your tokens on iEarn or lent them on Compound. If your stable coin is in its original form, you can ignore this option.

## **12. What are the dependencies of the protocol? How does risk bubble up?**

**Audits**

Curve smart contracts were [Audited](https://curve.fi/audits) by Trail of Bits\[10], Quantstamp\[11]. However, security audits don't eliminate risks completely.

**Admin keys**

The curve is fully decentralized with the launch of Curve DAO. There's an [Emergency DAO](https://dao.curve.fi/emergencymembers) that is able to pause the pools during the first 2 months in existence and Curve DAO can unpause them at any time.

Curve Emergency DAO has 9 members and 59.999% support and 51% quorum Curve Emergency DAO can act when there's a danger of loss of funds and call the kill\_me function of Curve Pool contracts which disables all functionality except for withdrawals. Curve pools can be reenabled back by either Emergency DAO or Curve DAO The Emergency DAO is controlled by Curve DAO which can add or remove Emergency members\[12].

Smart contracts CANNOT be upgraded. This limits actions in case of emergency but leaves users fully in control of their funds.

The curve will be transitioning to a DAO to be fully decentralized.

**Permanent loss of a peg**

If one of the stablecoins in the pool goes significantly down below the peg of 1.0 and never returns to the peg, it'll effectively mean that pool liquidity providers hold almost all their liquidity in that currency.

**Staking risks**

When staking you use multiple smart contract products each of which has its own risks

## **13: Does it have a governance token**

Yes, CRV token. CRV is the native utility token of the Curve protocol. It has four main use cases:  governance, LP rewards, boosting yields (as veCRV), and token burns.

**Governance**

Curve is a decentralized exchange and is community-governed. Decisions are made on-chain at [gov.curve.fi](https://gov.curve.fi) by CRV holders who vote-lock their tokens to convert them into veCRV.

**Rewards**

Liquidity pool rewards and incentives are paid in CRV to LPs based on the size of the pool share.

**veCRV**

veCRV stands for _vote-escrowed CRV_, a fancy name for CRV that’s been locked into the Curve protocol for a defined time. veCRV is used for voting in governance, boosting rewards, earning trading fees, and receiving airdrops. \[13]

### **14: How decentralized is**&#x20;

* **The Token**
  * **Unique Token Holders - 61695 \[14].**
* **Decision Making \[15]**
  * Anybody can create proposals but users need to follow the structure of a proposal which can be found by creating a new topic on the governance forum:[ https://gov.curve.fi/](https://gov.curve.fi)
  * Users who create proposals also need to create a corresponding CIP proposal at[ http://signal.curve.fi/](http://signal.curve.fi)
  * Using the signalling tool is completely free (no transaction fees) and you only need 1veCRV to create a proposal there.
  * Assuming you have at least 2,500 veCRV, you can also create an official DAO vote as long as it also comes with its topic presenting it on the governance forum.

**Staking (trading fees)**

CRV can now be staked (locked) to receive trading fees from the Curve protocol. A community-led proposal introduced a 50% admin fee on all trading fees. Those fees are collected and used to buy 3CRV, the LP token for the TriPool, which are then distributed to veCRV holders \[8].

### Boosting

One of the main incentives for CRV is the ability to boost your rewards on provided liquidity. Vote locking CRV allows you to acquire voting power to participate in the DAO and earn a boost of up to 2.5x on the liquidity you are providing on Curve.

### Voting

Once CRV holders vote-lock their veCRV, they can start voting on various DAO proposals and pool parameters

## 15. How is this exposed to layers in Defi:

### **What layers are upstream (built on top of the protocol)? Are other protocols that use it as a source of data/pricing oracle, or put funds into it?**

### **What layers are downstream (protocols/assets built on or put into the platform)? For example, yield farms are built on top of lending protocols**

Decentralized exchanges (DEXs) use Curve implicitly to facilitate currency conversions between coins that don’t otherwise have liquidity pairs. For example, there might be a liquidity pool for ETH/USDT and CRV/USDT, but no liquidity pool directly between ETH/CRV. What these DEXs do is first convert ETH to USDT, and then convert USDT to CRV, all in one action (using Curve under the hood), so that all a user sees is that their ETH has been converted into CRV. It is the base-layer foundation that many Defi apps sit on top of.

## **References:**&#x20;

1\.    Curve, [https://resources.curve.fi/base-features/understanding-curve](https://resources.curve.fi/base-features/understanding-curve)

2\.    Gemini, [https://www.gemini.com/cryptopedia/curve-finance-liquidity-provider-dao](https://www.gemini.com/cryptopedia/curve-finance-liquidity-provider-dao)

3\.    Defilama, [ https://defillama.com/protocol/curve](https://defillama.com/protocol/curve)

4\.    Curve Stats, [https://curve.fi/combinedstats](https://curve.fi/combinedstats)

5\.    Curve risks and reserves, [https://curve.fi/eurtusd/risks](https://curve.fi/eurtusd/risks)

6\.    Into the block, Assets, [https://app.intotheblock.com/insights/defi/protocols/curve](https://app.intotheblock.com/insights/defi/protocols/curve)

7\.    Defipulse, [https://defipulse.com/curve-finance](https://defipulse.com/curve-finance)

8\.    CRV Token, [https://resources.curve.fi/base-features/understanding-crv](https://resources.curve.fi/base-features/understanding-crv)

9\.    Attack, [https://twitter.com/emilianobonassi/status/1327716769969164292](https://twitter.com/emilianobonassi/status/1327716769969164292)

10\.  Trail of bits audit, [https://curve.fi/files/01-ToB.pdf](https://curve.fi/files/01-ToB.pdf)

11\.  Quantstamp Audit, [https://quantstamp.com/blog/quantstamp-audits-curve-finance-liquidity-mining](https://quantstamp.com/blog/quantstamp-audits-curve-finance-liquidity-mining)

12\.  Risks [https://curve.fi/eurtusd/risks](https://curve.fi/eurtusd/risks)

13\.  Governance, [https://academy.shrimpy.io/post/what-is-curve-finance](https://academy.shrimpy.io/post/what-is-curve-finance)

14\.  Unique Users, [https://dune.xyz/mrblock\_buidl/Curve.fi](https://dune.xyz/mrblock\_buidl/Curve.fi)

15\.  Curve Decision Making, [https://resources.curve.fi/guides/voting](https://resources.curve.fi/guides/voting)

16\.  Coingecko, [https://www.coingecko.com/en/coins/curve-dao-token](https://www.coingecko.com/en/coins/curve-dao-token)&#x20;

&#x20;


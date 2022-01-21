---
description: By Rahul Kanojia and Shivam Garg, 20 January 2022
---

# Compound

Compound is a decentralized protocol which establishes money markets with algorithmically set interest rates based on supply and demand, allowing users to frictionlessly exchange the time value of Ethereum assets.To achieve this The interest rate is set and updated every 10 seconds depending on the supply and demand of a specific asset \[1].

## 1. Is it a Protocol or a Token? - Both Protocol and Token

Compound is a lending protocol on the Ethereum blockchain that establishes money markets, which are pools of assets with algorithmically derived interest rates, based on the supply and demand for the asset. Suppliers (and borrowers) of an asset interact directly with the protocol, earning (and paying) a floating interest rate, without having to negotiate terms such as maturity, interest rate, or collateral with a peer or counterparty \[2].

The native Token of the Protocol is COMP, which is a Governance Token.

## 2. Category

Compound is a Lending protocol.

## 3. Does it have TVL?

Current TVL is $7.78 bln. as of 19 January 2022 \[4] based solely on the Ethereum blockchain.

## 4. What are its core metrics?

As of 19 Jan 2022:

* Liabilities $13.03 bln\[10]&#x20;
* Reserves Not available&#x20;
* Assets $5.6 bln\[10]&#x20;
* Treasury Not available&#x20;
* TVL: $7.78 bln \[4]&#x20;
* Ratio of Reserves to TVL (deposits only; unleveraged) 0.01092618\[6]&#x20;
* Ratio of Treasury to TVL (deposits only; unleveraged) Not available&#x20;
* Ratio of native Market Cap to TVL (deposits only; unleveraged) 0.1344 \[5]&#x20;
* Are they double-counting leverage? - NO

## 5. **Does the protocol have its own Token? - Yes**

Compound (COMP) is an ERC-20 asset that empowers community governance of the Compound protocol; COMP token-holders and their [delegates](https://compound.comradery.io/post/1464) debate, [propose](https://compound.comradery.io/post/1469), and [vote](https://compound.comradery.io/post/1449) on all changes to the protocol. By placing COMP directly into the hands of users and applications, an increasingly large ecosystem will be able to upgrade the protocol, and will be incentivized to collectively steward the protocol into the future with good governance **** \[7].

## 6. What chain is it on?

Currently, Compound only supports Ethereum main chain.

## 7. Could it be exploited?

Yes and it has been exploited earlier as well due to its heavy reliance on third party apps for orcales.&#x20;

Beyond just the protocol itself, many lending protocols rely on oracles to provide on-chain price data. Price oracles and price manipulation represent another attack vector for DeFi protocols and can be exploited.&#x20;

In November 2020, Compound’s price oracle was exploited by driving up the price of DAI by 30% on Coinbase Pro, resulting in $89 million worth of loans being liquidated.In September 2021, the Compound protocol suffered a bug stemming from a governance proposal that attempted to change the distribution ratios in the code. Due to the bug, roughly 500k COMP tokens, worth about $160,000,000 at that time, were available in the vulnerable contract and were distributed out to users that normally would not, and should not, have received them. Compound has acknowledged the bug and even took to Twitter to ask users to return the funds \[8].

## 8. What assets does it support?

Currently compound supports \[3]: &#x20;

* Dai (DAI)
* Ether (ETH)
* USD Coin (USDC)
* Ox (ZRX)
* Tether (USDT)
* Wrapped BTC (WBTC)
* Basic Attention Token (BAT)
* Augur (REP)
* Sai (SAI)

## 9. How does it combine the risks of those assets?

In the first place, it manages to offer the cheapest loans in the ecosystem, since the lender will always be able to have its capital whenever it wants, it can get a return on its assets even if it is only 10 seconds \[1].&#x20;

Also, the maximum price variation that the protocol accepts is 10% per hour. This security measure is excellent in case of market crashes, since it gives borrowers a small margin of time to secure their loans and avoid liquidations \[1].

## 10. Does it wrap and distribute assets?

Compound will generate a token (cToken) that represents the balance of the deposited token plus the accumulated interest every 10 seconds, obtained through the increase in the value of the cTokens. Thus, accruing interest is as easy as holding cTokens, which are transferable, tradable and programmable at the same time. To recover your assets plus the acquired interest it is as easy as redeeming the cTokens in Compound. Currently available: cZRX, zREP. cBAT, cUSDC, cWBTC, cSAI, cDAI and cETH \[1].

## 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

One can borrow up to 74% of the deposited capital. As soon as since it reaches 75%,  the position is liquidated so that the protocol can recover the borrowed capital. This is a very curious subject of the Compound protocol \[1].

## 12. What **are the dependencies of the protocol? How does risk bubble up?**

The Compound oracle is dependent upon the data that comes from high-volume exchanges like CoinbasePro, Bittrex, Poloniex, and Binance \[11].&#x20;

Compound does not enforce the stability of prices for a duration of time. So TWAP can vary significantly so if a borrower is not up to date with the latest exchange rate his/her position can be liquidated.

## 13. Does **it have a governance token?**

Yes, the aforementioned COMP token is an ERC-20 governance token, which means it gives its holders special voting rights. COMP holders can propose and vote on any network decision, from the amount of COMP rewarded for network usage to the types of assets accepted by the platform.&#x20;

Even the framework for Compound’s governance model itself can be voted on and changed by COMP holders. Anyone with 100,000 COMP tokens can create a new proposal. Additionally, through a process called the Compound Autonomous Proposal, anyone with 100 COMP tokens can also initiate the creation of a new proposal, but must first gather support from the community and have COMP tokens delegated to their proposal \[9].

## 14. How decentralized is it?

Like many other DeFi platforms, Compound rewards some users with its tokens for using the platform and providing liquidity, as an incentive. In order to fairly distribute the COMP governance token — and with it, agency over the Compound protocol and platform — the team allocated tokens to the project’s users in proportion to on-chain activity in April 2020. The more you lent or borrowed on Compound, the more COMP tokens you were rewarded. Over 10,000,000 COMP were distributed in this allocation, with approximately half going to users and the other half to the founders, team members, and investors in Compound \[9].

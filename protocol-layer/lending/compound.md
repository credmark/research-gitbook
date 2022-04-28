# Compound

Compound is a decentralized protocol which establishes money markets with algorithmically set interest rates based on supply and demand, allowing users to frictionlessly exchange the time value of Ethereum assets.To achieve this The interest rate is set and updated every 10 seconds depending on the supply and demand of a specific asset \[1].

### 1. Is It a Protocol or Token? - Both Protocol and Token

Compound is a lending   on the Ethereum blockchain that establishes money markets, which are pools of assets with algorithmically derived interest rates, based on the supply and demand for the asset. Suppliers (and borrowers) of an asset interact directly with the protocol, earning (and paying) a floating interest rate, without having to negotiate terms such as maturity, interest rate, or collateral with a peer or counterparty \[2].Currently compound only supports Dai (DAI), Ether (ETH), USD Coin (USDC), Ox (ZRX), Tether (USDT), Wrapped BTC (WBTC), Basic Attention Token (BAT), Augur (REP), and Sai (SAI) wrapped as ctokens \[3].

### **2. Category**

Compound is a Lending protocol.

### 3. **Does it have TVL?**

Yes, total TVL is $7.78 bln. as of 19 January 2022 \[4] It is on Ethereum mainnet only.

Current numbers can be found [here](https://defillama.com/protocol/compound).

#### How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?

It is calculated by Counting the tokens locked in the contracts to be used as collateral to borrow or to earn yield. Borrowed coins are not counted towards the TVL, so only the coins actually locked in the contracts are counted \[24].

## 4. Provide the following information at a protocol and pool level where appropriate

As of 19 Jan 2022

* Liabilities $13.03 bln \[10]&#x20;
* Reserves Not available&#x20;
* Assets $5.6 bln \[10]&#x20;
* Treasury Not available&#x20;
* Market Cap $1.045 bln \[4]&#x20;
* Ratio of Reserves to TVL (deposits only; unleveraged) 0.01092618 \[6]&#x20;
* Ratio of Treasury to TVL (deposits only; unleveraged) Not available&#x20;
* Ratio of native Market Cap to TVL (deposits only; unleveraged) 0.1344 \[5]&#x20;
* Are they double-counting leverage? NO

## 5. **Further details on the Token?**

**Markets where it’s available?** The list of markets can be found [here](https://coinmarketcap.com/currencies/compound/) \[23]&#x20;

**Liquidity:**&#x20;

* Circulating Supply - the total amount of tokens in circulation 6.52 mln \[22]&#x20;
* Total Supply - on-chain supply minus burned tokens 10 mln \[22]&#x20;
* Max Supply - theoretical maximum as coded 10 mln \[22]

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

Borrow/Lend Exposure Borrowers owe the prevailing interest rate of the asset they are borrowing. This is done by adding the Borrow Rate to the account’s Borrow Balance every Ethereum block. While a borrow is open, the Borrow Balance is ever-increasing. The borrow and interest is never required to be repaid unless the borrower becomes insolvent; otherwise, the borrower can choose to repay some or all of their borrow whenever they choose.\[25]

## 10. Does it wrap and distribute assets?

Yes, it does wrap its assets.&#x20;

Compound will generate a token (cToken) that represents the balance of the deposited token plus the accumulated interest every 10 seconds, obtained through the increase in the value of the cTokens. Thus, accruing interest is as easy as holding cTokens, which are transferable, tradable and programmable at the same time. To recover your assets plus the acquired interest it is as easy as redeeming the cTokens in Compound. Currently available: cZRX, cREP. cBAT, cUSDC, cWBTC, cSAI, cDAI and cETH \[1].

## 11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?

One can borrow up to 74% of your capital, since when it reaches 75% your position is liquidated so that the protocol can recover the borrowed capital. This is a very curious subject of the Compound protocol \[1].

## 12. **What are the dependencies of the protocol? How does risk bubble up?**

Yes compound oracle is dependent upon the data that comes from high-volume exchanges like CoinbasePro, Bittrex, Poloniex, and Binance \[11].&#x20;

As Compound does not enforce the stability of prices for a duration of time.So TWAP can vary significantly so if a borrower is not up to date with the latest exchange rate his/her position can be liquidated.

## 13. Does it have a governance token?

Yes, its name is COMP&#x20;

COMP is an ERC-20 governance token, which means it gives its holders special voting rights. COMP holders can propose and vote on any network decision, from the amount of COMP rewarded for network usage to the types of assets accepted by the platform. Even the framework for Compound’s governance model itself can be voted on and changed by COMP holders.Anyone with 100,000 COMP tokens can create a new proposal. Additionally, through a process called the Compound Autonomous Proposal, anyone with 100 COMP tokens can also initiate the creation of a new proposal, but must first gather support from the community and have COMP tokens delegated to their proposal \[9].

## 14. How decentralised is it?

Compound is the world’s fifth largest decentralised finance protocol, with more than $7 billion value locked, according to data provider DeFi Pulse\[4]. Like many other DeFi platforms, Compound rewards some users with its tokens for using the platform and providing liquidity, as an incentive.In order to fairly distribute the COMP governance token — and with it, agency over the Compound protocol and platform — the team allocated tokens to the project’s users in proportion to on-chain activity in April 2020. The more you lent or borrowed on Compound, the more COMP tokens you were rewarded. Over 10,000,000 COMP were distributed in this allocation, with approximately half going to users and the other half to the founders, team members, and investors in Compound \[9].

## 15. Additional Information

**VAR** -VaR could be calculated on the protocol level using the net exposure from Aave’s smart contracts and historical data of the tokens borrowed and lent. This metric is currently implemented in Risk Terminal of Credmark and was $2.4 bln as of 9 January 2022.&#x20;

**LCR** - also can be calculated on a protocol level and implemented in Risk Terminal. It was 25.6% as of 9 January 2022.&#x20;

**Are there any other metrics that might be useful? Like Sharpe Ratio** Yes, Sharpe ratio could be useful to compare against other protocols in lending.

## 16. **How is this exposed to layers in Defi**

#### What layers are upstream (built on top of the protocol)? Are there other protocols that use it as a source of data/pricing oracle, or put funds into it?&#x20;

Decentralised exchanges (DEXs) use Compound inside to operate.Basically interacting with compound via COMP token.&#x20;

Some of the examples are:&#x20;

* Dharma is a smart-wallet app that lets users deposit dai to earn interest easily. It also allows them to easily pay each other in dai, much like Venmo. While dai has not been the most popular asset on Compound lately (USDC and USDT have), each depositor and borrower on Dharma still earns some COMP each day as it gets distributed.&#x20;
* PoolTogether is a lossless lottery. Users deposit their funds with PoolTogether in order to win a chance at winning all the interest earned by everyone else who did the same. PoolTogether has a weekly dai pool and a daily USDC pool, but their returns have been hammered by the way liquidity mining has changed the market. "PoolTogether contracts are earning COMP and currently, the value of that COMP is actually greater than the value of the interest accruing to the prizes!," Leighton Cusack, the founder, told CoinDesk in an email. "However, when we designed the protocol we did not have COMP in mind so there is not a mechanism right now to re-distribute it to depositors or include it in the prize."

**What layers are downstream (protocols/assets built on or put into the platform). For example, yield farms are built on top of lending protocols**&#x20;

Compound oracle takes data from CoinbasePro, Bittrex, Poloniex, and Binance \[11].

## 17. Smart Contract information&#x20;

**List the protocol´s smart contract address**&#x20;

Curve Finance protocol address: [0x3fda67f7583380e67ef93072294a7fac882fd7e7](https://etherscan.io/address/0x3fda67f7583380e67ef93072294a7fac882fd7e7) \[12].&#x20;

**List the Token´s smart contract address**&#x20;

COMP token tracker address: [0xc00e94cb662c3520282e6f5717214004a7f26888](https://etherscan.io/address/0xc00e94cb662c3520282e6f5717214004a7f26888) \[13].&#x20;

**Are there any other relevant smart contracts?**&#x20;

Yes, assets compound currently currently support have their unique addresses listed on etherscan. [Here's the list](https://etherscan.io/accounts/label/compound) of all the assets and their addresses.

## **References:**&#x20;

1. Medium, https://arnauramiomateu.medium.com/deep-dive-into-compound-protocol-and-money-markets-157f30c493b7&#x20;
2. Compound, https://compound.finance/documents/Compound.Whitepaper.pdf&#x20;
3. Gemini, https://www.gemini.com/cryptopedia/what-is-compound-and-how-does-it-work#section-how-compound-crypto-liquidity-pools-work&#x20;
4. Defipulse, https://defipulse.com/compound&#x20;
5. Coinmarketcap, ,https://coinmarketcap.com/currencies/compound/&#x20;
6. Compound Treasury, https://compoundtreasury.com/&#x20;
7. Compound, https://compound.finance/governance/comp&#x20;
8. Crytoeq, https://www.cryptoeq.io/corereports/compound-abridged&#x20;
9. Gemini,https://www.gemini.com/cryptopedia/compound-crypto-defi-decentralized-finance#section-comp-governance-token&#x20;
10. Compound, https://compound.finance/markets&#x20;
11. CoinkDesk Audit, https://www.coindesk.com/tech/2020/06/19/defi-startups-built-on-compound-weigh-what-to-do-with-200-comp-tokens/&#x20;
12. Etherscan, https://etherscan.io/address/0x3fda67f7583380e67ef93072294a7fac882fd7e7&#x20;
13. Etherscan, https://etherscan.io/address/0xc00e94cb662c3520282e6f5717214004a7f26888&#x20;
14. Etherscan, https://etherscan.io/address/0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5&#x20;
15. Etherscan, https://etherscan.io/address/0x5d3a536E4D6DbD6114cc1Ead35777bAB948E3643&#x20;
16. Etherscan, https://etherscan.io/address/0xb3319f5d18bc0d84dd1b4825dcde5d5f7266d407&#x20;
17. Etherscan, https://etherscan.io/address/0x6c8c6b02e7b2be14d4fa6022dfd6d75921d90e4e&#x20;
18. Etherscan, https://etherscan.io/address/0x39aa39c021dfbae8fac545936693ac917d5e7563&#x20;
19. Etherscan, https://etherscan.io/address/0xC11b1268C1A384e55C48c2391d8d480264A3A7F4&#x20;
20. Etherscan, https://etherscan.io/address/0xf5dce57282a584d2746faf1593d3121fcac444dc&#x20;
21. Etherscan, https://etherscan.io/address/0x158079ee67fce2f58472a96584a73c7ab9ac95c1&#x20;
22. Coingecko, https://www.coingecko.com/en/coins/compound&#x20;
23. Coinmarketcap, https://coinmarketcap.com/currencies/compound/&#x20;
24. Defilama, https://defillama.com/protocol/compound&#x20;
25. Medium, https://medium.com/compound-finance/borrowing-assets-from-compound-quick-start-guide-f5e69af4b8f4

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| Deadsec        | 0x1A2E1d4553d33c080746A056AA3F832823fADB51 | 0 $CMK (internal) | Original version |


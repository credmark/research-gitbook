# Minimum Risk Rate of DeFi

## Executive Summary

Fragmented and diverse nature of decentralized finance ecosystem necessitated developing a framework similar to risk-free rate in traditional banking. Current paper addresses this problem by establishing methodology called Minimum risk rate of DeFi.

## Context

Since risk-free rate received so much negative feedback as a spurious and impractical concept, it makes sense to fix it in the to-be-built DeFi landscape. It’s recommended to use a term “minimal risk rate” instead in DeFi.

## TradFi

As mentioned, the traditional concept of risk-free rate has a theoretical nature. The current report is aiming at developing a more practical framework at the risk-free rate native to DeFi and its application.

In order to understand the concept of the risk-free rate, it’s important to understand its context in traditional finance (TradFi).

### Definition

Risk-free rate is normally a rate where there is no risk, primarily of not getting paid on the maturity date. Normally risk-free rate is a rate of overnight deposit at the central bank because the Government can always repay its debt by simply printing more money. It’s overnight (for 1 business day) because if the tenor of the deposit is longer there is arguably a higher liquidity risk that needs to be offset by a higher premium.

Not all Governments have enough credibility locally and internationally, which is usually reflected in the currency worth (exchange rate). If a country has substantial international debt to repay it’s not as simple as just printing more money, there have to be underlying fundamentals supporting the repayment.

Market liquidity depth is also an important consideration - although Switzerland is a credible government its size won’t be able to accommodate numerous international deposit institutions so size matters.

Depending on the structure of the government and its monetary policy there are different ways of defining risk-free rates. Let’s take the U.S. market as an example for the further assessment of TradFi system.

### U.S. Monetary System

The US Government sets the following two goals to the Federal Reserve (U.S. central bank) for the monetary policy: maximum employment and stable prices, which means low, stable inflation. Both imply the third important goal which is moderate long-term interest rates \[1], in other words, support for long-term growth.

To fulfil these goals, Fed has five monetary tools that are usually associated with the primary financial markets: reserve requirements, the discount rate (loans to deposit institutions), open market operations (debt market), the interest paid on reserves deposited (interbank deposit market), and overnight reverse repurchase agreements (repo market). The former three tools are traditional and open market operations is by far the most frequently used and the largest \[2].

Open market operations (OMO) is simply buying and selling U.S. government securities in order to align the yield with the publicly stated Fed funds rate target. Fed funds rate is an overnight money market target set by Federal Open Market Committee (FOMC) \[3]. All other tools usage is also aligned with the FOMC decisions.

Here is an example of how OMO tool is used. If the FOMC believes the economy is overheating (abnormal price growth, inflation) they would raise the target for the federal funds rate. Fed trading unit will then start selling government securities collecting payments from banks and therefore reducing the balance of their reserves. Increased supply of government securities drives securities prices down and yield up to align with the new federal funds target. In the short term currency might depreciate however in the mid-term it should appreciate attracted by the higher yields from international investors.

In summary, TradFi has the following infrastructure bottom-up:

1. Primary target audience of risk-free rate interventions are large deposit institutions, which then pass those changes to end users including mortgage holders
2. Main tool - open market operations is performed by controlling the debt market, the biggest basis asset market
3. Monetary policy is enforced by aligned usage of tools that involve interventions in core markets
4. U.S. monetary policy goals are maximum employment and prices stability, including moderate 30 year funding rates
5. The rate is actively controlled to achieve prosperity goals for the nation
6. In order to claim risk-free status, government must be credible and economy large/diversified enough to support international demand (issuer)
7. Risk-free rate is an overnight deposit rate in local currency to central bank of a credible government

## DeFi

Let’s compare TradFi architecture to DeFi (with numbers corresponding to TradFi section summary).

### **1.**  Target Audience of Minimal Risk Rate

Crypto world is still in its infancy and dominated by concentrated amount of players with significant resources (whales). This clientele usually has robust risk function, high sustainability and low risk mandate, which necessitates placing funds at a minimal risk rate. In this sense, DeFi is similar to TradFi.

### **2.**          The Biggest Basis Asset Market

In DeFi the biggest non-derivative market is lending and borrowing market, for example Maker is the largest DeFi protocol by total value locked in USD equal to USD 18 bln. \[4].

### **3.**          Alignment Across Markets

DeFi ecosystem by definition is fragmented. Alignment is achieved through operation of arbitrageurs - speculators that are looking for extracting profit from misalignments in yields.

### **4.**          Goals

Similarly there is no central point of control, hence no explicitly stated overarching goal. However organizations, especially big, understand and willing to contribute to the long-term growth of DeFi industry. Given banking existed for hundreds of years it makes sense to assume that best goals for DeFi are the same:

* Maximum employment of DeFi community
* Stable prices, including low inflation. Note that in DeFi inflation is different, it’s associated not with having more quantity of currency from one issuer but rather limited quantity from increasing number of issuers.
* Long-term projects (usually related to infrastructure) supporting environment

### **5.**          Control

In general, interest rates are passively controlled by platform pre-built logic driven by supply and demand of funds. Logic varies across different platforms.

### **6.**          Credible Issuer with High Market Depth

Stable means of payment in crypto could be classified into the following categories \[5]:

* Centralised Finance (CeFI) stablecoins - USDC, USDT, BNB
* DeFi stablecoins (fully backed by third party assets) - DAI
* Algorithmic stablecoins - UST, FRAX, FEI (different to others as they proactively control supply and demand like Fed)
* Algorithmic stableassets - RAI

Also, it could be the biggest Level 1 DeFi tokens like ETH, SOL or AVAX. These tokens also have an additional utility of being able to be used as gas payment on associated chains. On the other hand, their disadvantage is that the market price to fiat is volatile. Since the real economy is based on fiat market price volatility represents a significant source of risk.

### **7.**          Tenor and Counterparty

DeFi landscape of platforms is highly concentrated and dominated by big players. Although there is higher liquidity risk, cryptocurrencies might accrue interest and can be withdrawn from borrowing platforms intraday.

## Minimum Risk Rate of DeFi 1.0

Assuming the perspective of the user and community as a whole, the minimum risk rate is defined as:

* TVL weighted average rates from Aave and Compound per each stablecoin USDT, USDC and DAI (that is majorly based on ETH collateral and pegged to USD 1-to-1)
* Which are then weighted based on On-chain Volume in USD bln.

This approach provides the best alignment given the provided background.

Example as of 15 February 2022:

|                       | Aave  | Compound |
| --------------------- | ----- | -------- |
| TVL, in USD bln \[4]. | 10.85 | 7.22     |

&#x20;

| Currency | Deposit rate, Aave | Deposit rate, Compound |  TVL-weighted rate | On-chain Volume, in USD bln. \[6] |
| -------- | ------------------ | ---------------------- | ------------------ | --------------------------------- |
| USDT     | 2%                 | 2.31%                  | 2.12%              | 116.24                            |
| USDC     | 1.86%              | 1.67%                  | 1.78%              | 65.5                              |
| DAI      | 2.27%              | 2.42%                  | 2.33%              | 12.42                             |

&#x20;Based on these inputs, minimum risk rate equals to 2.02%. It is significantly higher than the Fed Funds Rate of 0.25%.&#x20;

### Other options for Minimum Risk Rate

* **Staking yields of the largest L1 token, ETH as a currency**\
  Although it’s arguably more important in the long-term it introduces significant price volatility that is not in line with the assumed community goals. This risk could be managed through having consumer products from the real economy denominated in ETH, such as rental costs.
* **Yield received from Liquidity Providing in stablecoins to the largest DEXs**\
  From the user perspective it might represent minimal risk. However, it wouldn't have sufficient market depth and is not aligned with the goals of the DeFi community.
* **Implied Futures Yields**\
  Biggest market is Perpetual futures. Although carry trading (hence deriving implied yield) is possible, it’s unstable as the payments are based on the market sentiment. If there are more buyers than sellers then futures are sold at a premium and vice versa. Instability of yield is also not addressing DeFi community goals.

References

1. What is the Fed: Monetary Policy, Accessed on 14 February 2022\
   [https://www.frbsf.org/education/teacher-resources/what-is-the-fed/monetary-policy/](https://www.frbsf.org/education/teacher-resources/what-is-the-fed/monetary-policy/)&#x20;
2. Federal Reserve Bank of San Francisco, Accessed on 14 February 2022  [https://www.frbsf.org/education/teacher-resources/what-is-the-fed/monetary-policy/](https://www.frbsf.org/education/teacher-resources/what-is-the-fed/monetary-policy/)
3. Fred Economic Data, Accessed on 14 February 2022\
   [https://fred.stlouisfed.org/series/FEDFUNDS](https://fred.stlouisfed.org/series/FEDFUNDS)&#x20;
4. DeFi Pulse, Accessed on 14 February 2022\
   [https://www.defipulse.com/](https://www.defipulse.com)&#x20;
5. How to DeFi: Advanced\
   [https://www.coingecko.com](https://www.coingecko.com)
6. The Block, Accessed on 15 February 2022\
   [https://www.theblockcrypto.com/data/decentralized-finance/stablecoins/adjusted-on-chain-volume-of-stablecoins-monthly](https://www.theblockcrypto.com/data/decentralized-finance/stablecoins/adjusted-on-chain-volume-of-stablecoins-monthly)

&#x20;

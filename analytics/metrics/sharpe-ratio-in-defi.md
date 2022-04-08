# 🚀 Sharpe Ratio in DeFi

## Executive Summary

With significant growth in return and the number of DeFi tokens, it’s important to make risk-weighted decisions. Sharpe ratio is a traditional measure of risk-adjusted returns, that allows the comparison of different assets and portfolios.

To apply it effectively in DeFi one should know Sharpe ratio application assumptions and limitations. One of the main limitations is that risk is defined as the volatility of both upside and downside, which ignores the fact that upside potential is beneficial for investors.

## Background

The Sharpe ratio was created by William Sharpe, the 1990 winner of the Nobel Prize in economic sciences. Sharpe ratio measures investment portfolio performance. It represents the return of an asset, without taking into account the “risk-free” interest rate and indicates the return percentage for each risk unit carried by the investment \[1].

Using the Sharpe ratio as part of your fundamental analysis strategy helps to provide important financial information that can be used to make smarter trading and asset management decisions.

Sharpe ratio is defined as:

![](<../../.gitbook/assets/image (6).png>)

Sharpe ratio can be also used to construct or analyse performance of a portfolio.

Let’s consider an example: investment into Asset X provides an expected return of 5% per annum and a standard deviation of 3.5% per annum. Sharpe ratio given risk-free rate is 0.25% equals 1.36.

In traditional finance, the following decision making is applied when using Sharpe ratio \[2]:

* Under 1.0 is considered bad
* 1.0 is considered acceptable or good
* 2.0 or higher is rated as very good

Hence Sharpe ratio of 1.36 is a good level for investment purposes.

## Crypto Market

Crypto markets are associated with abnormal returns and volatility.

Let’s try to apply the same concept to cryptocurrencies. We’ve used different parameters for sampling and holding periods to understand index behaviour. Instead of risk free rate, we’ve used [the minimum risk rate introduced by Credmark](https://docs.credmark.com/credmark-risk-library/analytics/data/modeling/minimum-risk-rate-of-defi) recently.

Figure 1 provides an analysis of monthly returns for 23 DeFi tokens sampled over trailing 3 months, 6 months and 1 year from 19 January 2022.

![Figure 1](<../../.gitbook/assets/image (7).png>)

Figure 2 - for fortnightly returns

![Figure 2](<../../.gitbook/assets/image (8) (1) (1).png>)

Figure 3 - for weekly returns

![Figure 3](<../../.gitbook/assets/image (6) (1).png>)

Figure 4 - for daily returns

![Figure 4](<../../.gitbook/assets/image (12).png>)

In a tabular form top three DeFi tokens based on 3 months, 6 months, and yearly sampling:

| Holding Period | Yearly sampling            | 6 months sampling          | 3 months sampling      |
| -------------- | -------------------------- | -------------------------- | ---------------------- |
| Daily          | **ETH**, **LINK**, **SOL** | ZRX, **LINK**, AVAX        | UNI, **LINK**, ZRX     |
| Weekly         | **CRV**, **ETH**, **SOL**  | **CRV**, ZRX, **ETH**      | **CRV**, BAT, MANA     |
| Fortnightly    | **ETH**, **CRV**, **SOL**  | **CRV**, **LINK**, **SOL** | **LINK**, KNC, AVAX    |
| Monthly        | **SOL**, **LINK**, MANA    | **CRV**, AAVE, FEI         | **CRV**, **LINK**, UNI |

&#x20;Most consistent results are produced by CRV, ETH, SOL, and LINK.

Based on the quantitative and qualitative considerations, including historical data availability and the fast pace of changes in crypto markets, we’ve come up with the following parametrization that is seen as most appropriate.

## Sharpe Ratio Methodology

Recommended parameterization for using Sharpe Ratio in DeFi is:

&#x20;

![](<../../.gitbook/assets/image (4).png>)

[Minimum risk rate methodology is covered in a separate document](../data/modeling/risk-free-rate.md). Time horizon and sampling parameters are selected for relatively short time frames due to the fast pace of innovation and nascency of the DeFi ecosystem. The rapid change in the environment of crypto markets might require more frequent rebalancing, so a two-week return appears more appropriate. 6 months sampling period is also supported by newly minted tokens not having sufficient historical data.

## Index Application

The selected parameterization produces the following results as of 19 January 2022:

![Figure 5](<../../.gitbook/assets/image (9).png>)

For example, the top Sharpe ratio is produced by CRV and equals to (12.65% - 2%/26) / 26.1% = 0.48.

Although Sharpe ratio is a traditional measure, it’s important to understand it conceptually in light of all underlying assumptions and parameters.

As can be seen, top DeFi assets show smaller Sharpe ratios in the current parametrization compared to traditional financial instruments, classified as “bad” investment. This is due to the high volatility of returns inherent in the crypto markets, in the example above its 26.1%. Most of the volatility is upside which is in fact beneficial for investors. Sharpe ratio is direction-agnostic so capturing the upside potential as a risk is a known limitation of the Sharpe ratio, which is addressed by the Sortino ratio. Sortino ratio (to be detailed in another article) is a better metric to use for higher risk investments and could be a better metric for DeFi in its nascency.

However, DeFi Sharpe ratios would improve and show better results than assets in TradFi once there is simply more history. In the example, the above-median fortnightly return is 12.65% which in annualized terms is 328%.

Sharpe index is also a useful tool to compare DeFi tokens performance and construct an optimal risk-return portfolio. And Figure 5 is an example of such comparison as of 19 January 2022.

## References

1. Wikipedia, accessed on 24 February 2022\
   [https://en.wikipedia.org/wiki/Sharpe\_ratio](https://en.wikipedia.org/wiki/Sharpe\_ratio)
2. Business Insider, accessed on 24 February 2022\
   [https://www.businessinsider.com.au/sharpe-ratio?r=US\&IR=T](https://www.businessinsider.com.au/sharpe-ratio?r=US\&IR=T)&#x20;

## Contributors

| Discord Handle    | ETH Address                                    | Reward           | Contribution     |
| ----------------- | ---------------------------------------------- | ---------------- | ---------------- |
| **atulemis#0983** | **0x5fb7584838fB467e90bb8a1df3a278482e34E856** | 0 CMK (internal) | Original version |

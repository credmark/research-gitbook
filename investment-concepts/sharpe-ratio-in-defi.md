# Sharpe Ratio in DeFi

## Executive Summary

With significant growth in return and the number of DeFi tokens, it’s important to make risk-weighted decisions. Sharpe ratio is a traditional measure of risk-adjusted returns, that allows the comparison of different assets and portfolios.

To apply it effectively in DeFi one should know Sharpe ratio application assumptions and limitations. One of the main limitations is that risk is defined as the volatility of both upside and downside, which ignores the fact that upside potential is beneficial for investors.

## Background

The Sharpe ratio was created by William Sharpe, the 1990 winner of the Nobel Prize in economic sciences. Sharpe ratio measures investment portfolio performance. It represents the return of an asset, without taking into account the “risk-free” interest rate and indicates the return percentage for each risk unit carried by the investment \[1].

Using the Sharpe ratio as part of your fundamental analysis strategy helps to provide important financial information that can be used to make smarter trading and asset management decisions.

Sharpe ratio is defined as:

![](<../.gitbook/assets/Bildschirmfoto 2022-04-07 um 18.00.46.png>)

Sharpe ratio can be also used to construct or analyse the performance of a portfolio.

Let’s consider an example: investment into Asset X provides an expected return of 5% per annum and a standard deviation of 3.5% per annum. Sharpe ratio given risk-free rate is 0.25% equals 1.36.

In traditional finance, the following decision making is applied when using Sharpe ratio \[2]:

* Under 1.0 is considered bad
* 1.0 is considered acceptable or good
* 2.0 or higher is rated as very good

Hence Sharpe ratio of 1.36 is a good level for investment purposes.

## Crypto Market Environment

Crypto markets are associated with abnormal returns and volatility.

Let’s try to apply the same concept to cryptocurrencies. We’ve used different parameters for sampling and holding periods to understand index behaviour. Instead of risk free rate, we’ve used [the minimum risk rate introduced by Credmark](https://docs.credmark.com/credmark-risk-library/analytics/data/modeling/minimum-risk-rate-of-defi) recently.

Figure 1 provides an analysis of monthly returns for 23 DeFi tokens sampled over trailing 3 months, 6 months and 1 year from 19 January 2022.

![Figure 1](<../.gitbook/assets/image (5).png>)

Figure 2 - for fortnightly returns

![Figure 2](<../.gitbook/assets/image (1).png>)

Figure 3 - for weekly returns

![Figure 3](<../.gitbook/assets/image (2).png>)

Figure 4 - for daily returns

![Figure 4](<../.gitbook/assets/image (3).png>)

In a tabular form top three DeFi tokens based on 3 months, 6 months, and yearly sampling:

| Holding Period | Yearly sampling            | 6 months sampling          | 3 months sampling      |
| -------------- | -------------------------- | -------------------------- | ---------------------- |
| Daily          | **ETH**, **LINK**, **SOL** | ZRX, **LINK**, AVAX        | UNI, **LINK**, ZRX     |
| Weekly         | **CRV**, **ETH**, **SOL**  | **CRV**, ZRX, **ETH**      | **CRV**, BAT, MANA     |
| Fortnightly    | **ETH**, **CRV**, **SOL**  | **CRV**, **LINK**, **SOL** | **LINK**, KNC, AVAX    |
| Monthly        | **SOL**, **LINK**, MANA    | **CRV**, AAVE, FEI         | **CRV**, **LINK**, UNI |

&#x20;Most consistent results are produced by CRV, ETH, SOL, and LINK.

## Sharpe Ratio Methodology

Based on the quantitative and qualitative considerations, including historical data availability and fast pace of changes in crypto markets, Credmark recommends the following parametrization of Sharpe ratio:

&#x20;

$$
SharpeRatio_{CMK} = ((R_{ca}-R_{mrr})/\sigma(R_{ca})
$$

, where:

$$R_{ca}$$ - mean of crypto asset ca scaled daily returns sampled over the period of last six months. Scaled daily return is defined as $$(P_t/P_{t-1}-1)*\sqrt{365}$$, using the square root of time rule \[3]. Daily returns are assumed to have i.i.d. property.

$$R_{mrr}$$-minimum risk rate, which methodology is covered in a separate [report](broken-reference).

$$\sigma_{ca}$$-standard deviation of trailing $$R_{ca}$$ over the past six months.

Six months investment horizon provides convenience across:&#x20;

* Newly issued tokens that don’t necessarily have a sufficiently long history
* A trade-off between being not too static and too volatile

### Application

The selected parameterization produces the following results for 100 top traded tokens as of 27 January 2022:

![Figure 5 - Credmark recommended Sharpe Ratio for top traded 100 tokens as of 27 January 2022](https://lh6.googleusercontent.com/QgqTkInhH9Q8cvmw-3k3PvgX3I-zPHxcU4-Ixhuj7UOn2wWipE1eKQIHM-M2YlRV-EATFSVwQfJfYDRL9iG6JEFlkqtw-v42gwAGcWyofRKQl9vE\_tZ-UqWJivpUOuxB9kCibNU)

Overall results are lower than 1 (“bad investment”) that is explained by the bear market started in December 2021. As of 27 January 2022, ETH is the token with the one of the highest Sharpe ratios, that equals to 0.093.

Figure 6 shows ETH Sharpe ratio evolution in time since January 2019.

![Figure 6 - Sharpe ratio of ETH token time-series](https://lh3.googleusercontent.com/Pn1fQDnpVsow4C-7IdNugoN6ChtLbW0h5PoDsj5anfSCthuOPOgBICROcBvqJxNrFNqExMnpA99c0IckAaaiyOYzgWjySRT9B0CxrowTPujpHzX9wbdgs0Bw26IA-\_yovQA8lpk)

As can be seen its Sharpe ratio varied from 0 to 8 over the last two years. Majority of time it stayed above 1 (“good investment”).

ETH Sharpe index declined by 4 points from December 2021 to January 2022 that coincided with the beginning of the bear market. The drop is equivalent to May 2021 crash when it decreased from 5 to 1 over the span of two months.

## References

1. Wikipedia, accessed on 24 February 2022\
   [https://en.wikipedia.org/wiki/Sharpe\_ratio](https://en.wikipedia.org/wiki/Sharpe\_ratio)
2. Business Insider, accessed on 24 February 2022\
   [https://www.businessinsider.com.au/sharpe-ratio?r=US\&IR=T](https://www.businessinsider.com.au/sharpe-ratio?r=US\&IR=T)&#x20;
3. On time-scaling of risk and the square-root-of-time rule, accessed on 15 April 2022\
   [https://www.sciencedirect.com/science/article/abs/pii/S0378426606000070](https://www.sciencedirect.com/science/article/abs/pii/S0378426606000070)

## **Version Control**

| **Version** | **Change Summary**                    | **Author(s) (Discord Handle, ETH Address, Reward)**                                         | **Reviewer(s) (Discord Handle, ETH Address, Reward)**                                                                                                                                | **Submission Date** |
| ----------- | ------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------- |
| 1.0         | Created                               | <p>atulemis#0983,<br>0x5fb7584838fB467e90bb8a1df3a278482e34E856,</p><p>0 CMK (internal)</p> | <p>Harri Tarni,<br>0x295B61866dAA53a76CE4b3a927EFAF0059b4a90A,<br>0 CMK (internal)<br><br>JeSuisCollier#0315,<br>0x2588B6be7A132e137Be9A6f08eB09C359688b150,<br>0 CMK (internal)</p> | 1 March 2022        |
| 2.0         | Change of recommended parametrization | <p>atulemis#0983,<br>0x5fb7584838fB467e90bb8a1df3a278482e34E856,</p><p>0 CMK (internal)</p> | <p>Harri Tarni,<br>0x295B61866dAA53a76CE4b3a927EFAF0059b4a90A,<br>0 CMK (internal)<br><br>JeSuisCollier#0315,<br>0x2588B6be7A132e137Be9A6f08eB09C359688b150,<br>0 CMK (internal)</p> | 20 April 2022       |

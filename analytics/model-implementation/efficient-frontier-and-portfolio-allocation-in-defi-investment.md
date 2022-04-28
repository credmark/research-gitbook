---
description: Version 1.0, updated on 2022.04.24
---

# Efficient Frontier and Portfolio Allocation in DeFi Investment

### Executive Summary <a href="#_nq3i1dbtobxj" id="_nq3i1dbtobxj"></a>

1. When Sharpe Ratio (W. Sharpe, 1966) built up the risk/reward ratio as a performance measure of portfolio, Efficient Frontier, as a cornerstone to Modern Portfolio Theory (H. Markowitz, 1952), has already adopted it to build a portfolio with optimal performance\*.
2. What Markowitz tried to solve is the portfolio allocation problem when investing into a diversified set of stocks. Efficient frontier is his answer to the problem, i.e. to optimize for the lowest level of risk with a given return target, or alternatively, the highest expected return for a defined level of risk.
3. With Markowitz’s framework, it reduces the variability of the portfolio return and hence increases the Sharpe ratio. This has caught the interest of Wall Street and it became the foundation for mutual funds and hence the profession of portfolio manager is born.
4. Efficient frontier is very sensitive to the input, making it a double-sided sword that needs mindful application. With a few contemporary enhancements and generalizations of the theory, we can use it to profile different tokens’ risk characteristics and optimize a portfolio with risk and/or return targets. Efficient frontier still finds its usefulness in the world of DeFi token investment.

\* Markowitz is truly a pioneer leading the age to come. His MPT utilized the return-deviation measure in the model while Sharpe formalized it later.

### Introduction <a href="#_f2cbc8l60jbr" id="_f2cbc8l60jbr"></a>

When Markowitz broke the ground of portfolio analysis with Modern Portfolio Theory (ca. 1952), there was nothing likewise in this field ever before. His creative application of risk/reward into the portfolio allocation problem is a start of quantitative portfolio management. As from the perspective of 70 years’ later, it’s an old gem to shed some light on portfolio building in the DeFi world.

### Theory <a href="#_f5xjw7mt5tbt" id="_f5xjw7mt5tbt"></a>

The theory was proposed on the stock market initially. We will reintroduce it in the context of the DeFi tokens.

1. Every token can be characterized with an expected return (an outlook for its future return) and risk (volatility of return). This is recorded in the covariance matrix .

![](<../../.gitbook/assets/0 (1)>)

1. With a portfolio of tokens, we can assign weights as capital allocated to each token. Nevertheless, the negative weights are permissive (shorting positions) and the same method can be used to solve the solution. This is denoted as vector .
2. The portfolio’s risk can be estimated with the covariance matrix of all the tokens and weights. This is calculated as a product between the weights and the covariance matrix ![](<../../.gitbook/assets/1 (1)>).
3. The portfolio’s return can be calculated with the expected return and the weights. This is calculated as the product between the weights and expected return ![](<../../.gitbook/assets/2 (1)>).

In order to solve the minimal risk for a given return target, we have the following constraints to be satisfied.

* The constraint for the weights is their sum shall be equal to 1 and with some weights need to be positive (shorting is allowed in the framework).
* The return shall be larger than the given level
* The risk shall be minimized

These conditions are expressed in following terms.

![](../../.gitbook/assets/3)

The process of solving this is a typical optimization problem in mathematics. Markowitz built up this mathematical framework for portfolio analysis. This is his Modern Portfolio Theory, or mean-variance analysis.

If we varied the target risk levels and solve the optimization problem, we will obtain the efficient frontier as the lower level of risk with a return target, or alternatively, the highest level of return with a risk target. This could be better illustrated in the figure below.

Each dot in the figure represents a portfolio composed of certain weights. It’s characterized by the expected return and the volatility of the such return. The optimization for the minimal risk at all possible levels of return would yield a boundary line, which represents the most efficient usage of the capital with minimized risk at a level of return. Any dots inside the boundary line represent portfolios with either lower return at a risk target, or higher risk at a return target. For example, the red dot inside the EF has higher risk than the green dot sitting on the EF on the same level of return, and lower return than the blue dot sitting on EF with the same level of risk. Such a boundary is called the efficient frontier.

### Walk-through Examples <a href="#_8coz1nipgtqo" id="_8coz1nipgtqo"></a>

Let’s take a break from the theory and look at some examples to understand it more clearly.

The first step to carry out the above analysis is to obtain the expected return and risk of the tokens. This brought out the (almost) most important point of practicing this kind of analysis. It is hard to obtain such returns and risk. For two reasons:

1. Unless we can travel in time, we can never know those values for certain. They can only be estimated from what we know of today. Common practice (as many textbooks do) is to use historical data. This is not realistic as it assumes a repeatable future like the history for every token and the correlation between them will remain constant.
2. What makes it worse is that the further calculations, i.e. the mean-variance optimization, is extremely sensitive to variations in these input values. Mostly on return inputs, less sensitive to the volatility inputs. If the input values are changed, even by relatively small amounts, the optimal portfolio weightings created by the model can swing and vary wildly. Such instability of the solution sensitive to the small changes in the input makes our analysis un-robust.

This poses a large limitation to the quality of the model output. There are a few ways to improve the estimation and mediate this limitation.

1. The first point could be counter-intuitive. It is that we shall avoid applying the allocation problem when possible. How could we introduce a model and not use it? We rather mean that we shall apply the model where it is appropriate. As we know the model is sensitive to the input data variation, we can apply the model broadly not in grain-line detail. The common practice is to divide our investment space into sectors and within the sector, we choose representative assets to use the model to perform optimization to the sector allocation.
2. We shall avoid using the sample covariance directly derived from the historical data but instead, we use “shrinkage estimators” for key inputs. This is proposed by Ledoit and Wolf (2004) to shrink the sample correlation matrix towards (in other words, averaging) to the constant correlation matrix. The constant correlation matrix is simply the correlation matrix where each diagonal element is equal to the pairwise average correlation across all assets.
3. When we have a view for the expected return, we can employ the Black-Litterman model to the subjective views of an investor with the market equilibrium vector of expected returns (the prior distribution) to form a new, mixed estimate of expected returns. The resulting new vector of returns (the posterior distribution), leads to intuitive portfolios with sensible portfolio weights.
4. We may also replace the risk model of return-variance with other metrics, such as semi-variance to reduce downside risk, CVaR (conditional VaR) to reduce tail risk, or hierarchical risk parity to cluster similar assets to mini-portfolios.

As a starting point, we take the suggested 1) to apply our analysis to a few representative tokens and 2) apply shrinkage to the sample covariance. The expected return is still obtained from historical data as if we look retrospectively..

Below figure shows the price movement during 2020-01-01 to now. From the recent two years’ history, there was a cycle starting from 2021-01-01 to 2022-04-01. We will use the data from this period.

![](<../../.gitbook/assets/5 (1)>)

The tokens are: BTC, ETH, UNI, COMP, AAVE, CRV, USDT. They consist of stable coins (USDT), DeFi foundation tokens (BTC and ETH), and DeFi large-cap (UNI, COMP, AAVE, CRV). Below figure shows the sharpe ratio of selected tokens.

![](<../../.gitbook/assets/6 (1)>)

As we break down the Sharpe Ratio back to average return and standard deviation, we plot them onto a figure as shown below. The slope passing through the point is the Sharpe ratio without the risk-free rate. This is how Markowitz’s finding was leading in 1952. Each dot represents a portfolio of 100% invested to that token.

This figure looks ordinary but we can fill it up with portfolios with weights in multiple tokens, instead of one token per portfolio. In the figure below, the large gray dots are the same as the previous figure but we have more small colored dots (colored according to its Sharpe Ratio, the purple/blue represent high and the green/yellow represent low) representing the portfolios with multiple tokens. The blue line is the efficient frontier. It illustrates the boundary of the small dots that can not go beyond towards the higher Sharpe Ratio, which is the left-top corner. The efficient frontier links the USDT, ETH and CRV. The USDT is of 0 risk and 0 return. The ETH has about 250% annualized return and 120% annualized standard deviation. And the CRV goes beyond ETH with close to 300% annualized return and 140% annualized standard deviation. The efficient frontier is the 2-dimensional visualization of the Sharpe Ratio.

![](../../.gitbook/assets/8)

To step back how the dots are formed, we start from a two-token case and gradually add more tokens. Below figure shows the USDT-ETH. Portfolios with different weights between the two tokens form a line linking the two dots.

![](<../../.gitbook/assets/9 (1)>)

After we add the third token, BTC, as we show below. There are more dots filling the void space between USDT, ETH and BTC. The dots are bounded by the profile of the dual-token portfolio of USDT-BTC, and BTC-ETH. As we add more tokens, we will add more boundaries formed between the dual-token portfolios between the newly added tokens to all existing tokens. And new dots will fill the void inside the boundary. As shown further below, we have a figure for USDT-ETH-BTC-COMP with COMP expanding the boundary to the lower-right corner.

![](../../.gitbook/assets/10)

![](<../../.gitbook/assets/11 (1)>)

USDT is considered as a riskless asset, occupying the (0,0) point. If we exclude it and only include the risky tokens, the more commonly visually recognizable efficient frontier appears in the figure below plotted for COMP-CRV-UNI-AAVE.

If we would have the maximized return, we shall have invested 100% in CRV. If we would have the minimal risk, we would have invested into the portfolio at the large red dot. Such a portfolio is with the weights of 32% CRV, 31% COMP, 22% UNI and 15% AAVE. It’s arguable that investment into the three non-CRV tokens would be losses. The return drops from 291% (all in CRV) to 118% (in four tokens). However, it does bring down the volatility from 140% (all in CRV) to 118% (in four tokens). The minimal risk portfolio is the most conservative portfolio. Practically, we will find an allocation along the efficient frontier, indicated by the box shown in the figure.

In summary, the mean-variance analysis produces the efficient frontier is a comprehensive view of the outcome of all possible combinations of the tokens in a portfolio. It represents an analysis framework from data to portfolio allocation decisions. This is such an important contribution from Markowitz to modern finance.

As we have noted earlier, there is a major limitation in applying this framework, which is how to estimate for the return and covariance and make the framework for practical use. We will continue the discussion in the section below.

### Application <a href="#_lxe3qwes9co" id="_lxe3qwes9co"></a>

To make efficient frontier working in practice, we have highlighted a few points earlier. You may scroll up to re-read them and I will also summarize below

1. Apply the model to the broad section instead of sorting out 100 or 1000 tokens,
2. Fix the covariance matrix and do not use sample covariance matrix directly
3. Apply a subjective view and mix it with current market equilibrium conditions.
4. Use more advanced models.

We will discuss each point in detail.

1. Divide into sectors and apply the EF model within the sector.

Schematically, we could have below sectors.

* Risk-less asset: stablecoins are cash-like, no or minimal return and also little volatility.
* Risky assets:
  * Stable asset: small return and small volatility, e.g. BTC
  * ETH: volatile but fundamental token for DeFi.
  * DeFi: below category can be further divided by market capitalization or grow/value.
    * DeFi Developed
    * DeFi Emerging

The historical and current data could guide us into categorization. We can plot EF with the top 100 tokens traded, shown in figures below. The left figure is with all the tokens and the right figure has removed the obvious outlier of LUNA/AXS/DOGE to have a better view of the rest.

![](<../../.gitbook/assets/13 (1)>) ![](<../../.gitbook/assets/14 (1)>)

We could see there the left half triangle of the figure is empty because the high-growth token is also with high risk (volatility). As we remember the analysis based on historical data is limited and could be the contrarian to the future, we shall exercise caution to the analysis and make good decisions of sector choice. In the event of busting, we only lose part of the portion that gets allocated to the sector.

The allocation to cash / BTC / ETH shall not be solved by the model as they are for the purpose of value-preserving and basic transactions. We apply the model into the asset allocation to the DeFi section. As an example, we choose CRV-MKR-AAVE. The EF is plotted in the figure below.

![](<../../.gitbook/assets/15 (1)>)

For maximum Sharpe ratio, CRV 91%, MKR 9%.

* Expected annual return: 280.8%
* Annual volatility: 134.6%
* Sharpe Ratio: 2.07

For minimal risk, CRV: 37%, MKR 33%, AAVE 30%.

* Expected annual return: 184.0%
* Annual volatility: 119.1%
* Sharpe Ratio: 1.54

The minimal risk allocation is almost ⅓ for each token. This was determined by the expected return and risk characteristics of the three tokens.

![](<../../.gitbook/assets/16 (1)>)

Above figure shows the covariance (above) and correlation matrix (below). The standard deviation (\~1.4) and correlation (\~0.5-0.6) between three tokens (CRV, MKR and AAVE) are similar. What’s different is the expected return of three tokens estimated from the historical data. In annualized terms, they are CR V 2.9, MKR 1.7 and SAVE 0.6. When the risk characteristics are similar, the expected return determines the weights in the portfolio.

Let’s choose another historical period to estimate the expected return, such as the period of downward price movement from 2021-10-01, the tokens’ expected return has largely slumped into negative figures, CRV 0.1 MKR -0.3 AAVE -0.7 and the correlation between them has also deteriorated to lower values. H

![](<../../.gitbook/assets/17 (1)>)

We will have a completely different allocation of weights for the optimal portfolio with max Sharpe ratio.

* Expected annual return: 6.3%
* Annual volatility: 137.9%
* Sharpe Ratio: 0.03
* Allocation: MKR 53% AAVE 35% CRV 12%

The EF plot has shown that the MKR and AAVE has become a much more stable asset, in standard deviation terms, CRV 1.4, MKR 0.96, AAVE 1.1. Therefore the allocation of MKR has increased in comparison to the drop of CRV as a more riskier holding.

![](<../../.gitbook/assets/18 (1)>)

1. Use a shrinked matrix and properly estimated expected return.

The EF is very sensitive to the input data. We have shown one example just above for different inputs of expected returns and covariance matrix.

We would like to illustrate this point with one further example.

For the 100 token data, we have calculated the Sharpe ratio for each token as shown below. It’s a “long-tail” figure. We added a figure to show the top 20. LUNA and AXS top the chart. Therefore, they will distort the allocation.

![](<../../.gitbook/assets/19 (1)>)

The top 20 are

![](<../../.gitbook/assets/20 (1)>)

The maximum Sharpe Ratio is for the portfolio of LUNA 51%, AXS: 41% and LEO 8%.

* Expected annual return: 5765.0%
* Annual volatility: 149.4%
* Sharpe Ratio: 38.58

If we remove them from the analysis, we would have obtained another set of more balanced allocations. Nevertheless, the ones chosen still top in the Sharpe ratio than the rest.

MATIC: 43%, SOL 29%, LEO 13%, FTM 5%, DOGE 4%, KDA 3%, ONE 2%.

* Expected annual return: 1788.9%
* Annual volatility: 118.0%
* Sharpe Ratio: 15.14

Such sensitivity makes the model a double-sided sword. If we can get the expected return right, the allocation is indeed optimal and efficient. If we do not get it right, we will allocate concentratedly to the very high risk tokens.

Hence, we will bring out the next section.

1. The Black-Litterman model

The Black-Litterman model combines the subjective views of an investor regarding the expected returns. We may specify our view towards the future growth. For example, we may specify projected absolute views on return, MATIC +40%, SOL +120%, SAND +30% and DOGE -20%.

The BL-EF model will calculate below allocations.

For maximum Sharpe ratio: MATIC 5%, SOL: 88%, SAND: 7%, DOGE 0

* Expected annual return: 57.8%
* Annual volatility: 142.3%
* Sharpe Ratio: 0.39

For minimal risk: MATIC 8%, SOL: 27%, SAND: 62%, DOGE 3%

* Expected annual return: 34.8%
* Annual volatility: 110.1%
* Sharpe Ratio: 0.30

Below figure shows the EF for such MATIC-SOL-SAND-DOGE portfolio.

The covariance (above) and correlation (below) matrices are shown below. The standard deviation of the tokens are MATIC 1.8, SOL 1.5, SAND 1.2 and DOGE 3.8. Except DOGE, the other three tokens are about 0.4-0.5 correlation to each other. The minimal risk portfolio allocation will make the tokens of small standard deviation to be high in weights. The max Sharpe ratio portfolio allocation will leverage between standard deviation (risk) and expected returns.

The BL model also takes input of relative views, such as MATIC +20% and SOL outperforms MATIC by 50%, SAND +30%, and SAND outperforms DOGE by 10%. The EF plot is shown below.

The portfolio allocations are below. The minimal risk portfolio allocations are almost the same as the previous absolute views. The minimal risk portfolio allocation is mostly impacted by the covariance matrix input. As the BL model mainly optimizes for the expected return so it is little impacted.

For maximum Sharpe ratio: MATIC 34%, SOL: 64%, SAND: 0%, DOGE 2%

* Expected annual return: 1226.6%
* Annual volatility: 135.7%
* Sharpe Ratio: 9.02

For minimal risk: MATIC 8%, SOL: 27%, SAND: 62%, DOGE 3%

* Expected annual return: 507.6%
* Annual volatility: 110.1%
* Sharpe Ratio: 4.59

1. Use non-mean-variance metric.

**Semivariance**

Instead of mean-variance, we could optimize for other metrics. Semivariance is a measurement of data that can be used to estimate the potential downside risk of an investment portfolio. Semivariance is calculated by measuring the dispersion of all observations that fall below the mean or target value of a set of data.

For the portfolio of MATIC-SOL-SAND-DOGE, we could obtain minimal semivariance allocation with MATIC 5%, SOL: 16%, SAND: 65%, DOGE 14%.

* Expected annual return: 383.1%
* Annual semi-deviation: 68.9%
* Sortino Ratio: 5.53

**Hierarchical Risk Parity (HRP)**

Hierarchical Risk Parity is a novel portfolio optimization method developed by Marcos Lopez de Prado. The advantages of this are that it does not require the inversion of the covariance matrix as with traditional mean-variance optimization, and seems to produce **diverse** portfolios that perform well out of sample. Contrary to maximizing returns, diversification is what HRP tries to achieve.

The initial allocation with HRP will result in allocations all into stable coins, as shown in figure below.

We excluded the stable coins and re-run the model and below figure shows a rather diversified allocation to the tokens.

Such portfolio will have a performance of

* Expected annual return:146.6%
* Annual semi-deviation: 75.9%
* Sharpe Ratio: 1.9

The details of such allocation and how hierarchical structure is formed for the mini-portfolios will be discussed in another article.

**CVaR**

CVaR (Conditional VaR) is a measure for the tail risk. In Markowitz's framework, we can set the objective function to minimize the tail risk instead. We have obtained such portfolio allocation,

* Expected annual return: 328.4%
* Conditional Value at Risk: 11.63%
* Allocation: SAND 0.82%, MATIC 9%, SOL 6%, DOGE 2.5%.

Below figure shows the solution space to optimize for CVaR.

### Conclusion <a href="#_y4wz2f8ddryi" id="_y4wz2f8ddryi"></a>

As a summary, the EF and mean-variance framework is an effective and efficient tool to obtain an optimal allocation to assets. Its ultra-sensitivity to the input (expected return and covariance matrix) is a double-sided sword to make it effective on the date it takes for the purpose and details the user shall be in control of. The framework proposed by Markowitz 70 years’ ago is still a spring for ideas as of today.

There have been many enhancements and generalizations in the framework of Markowitz. We shall have better estimation of the expected returns and covariance matrix, and we may not optimize for the mean-variance but rather CVaR, Semivariance or HRP, instead.

These are the best practices to be applied to practical use of the model for the good of DeFi investment.

### Contributor <a href="#contributor" id="contributor"></a>

| Author       | ETH Address                                | Contribution |
| ------------ | ------------------------------------------ | ------------ |
| ​kunlun#8324 | 0x109B3C39d675A2FF16354E116d080B94d238a7c9 | New article  |
|              |                                            |              |
|              |                                            |              |


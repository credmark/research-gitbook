---
description: By Joey Hirsh, 30 December 2021
---

# Aave and Compound Historical VaR

### Executive Summary

Value-at-Risk (VaR) is an estimate of the worst-case loss for a given portfolio given normal market conditions. The VaR is estimated assuming no changes to the portfolio over a set period of time. Several techniques are used to estimate VaR; we have used a historical method that is derived from historical price movements. We apply our VaR at a protocol level to Aave and Compound. The protocol level VaR is useful as it helps to quantify how much a portfolio – in this case, a DAO’s assets – is exposed to market risk on a net basis.

We computed VaR for Compound and Aave on 2 November 2021. At that time, Compound’s VaR was 19% higher than Aave’s. **The primary driver of this difference is that Compound had more concentrated liabilities in both BTC and ETH, which contributed more to VaR than Aave’s diverse portfolio.**

## Analysis

The historical VaR model considers variations in price over a specified time period, called the sampling period. The VaR model answers the question: "if I have similar market conditions in the future, what would be the 99th percentile worst-case loss for my current portfolio?". We use the 99th percentile as it is the standard in traditional finance. In order to generate estimated returns, we must specify the length of time for which we expect to hold the portfolio’s position; this is called the holding period.

In the tables that follow, we apply the historical VaR model to Aave and Compound, using a 99 percentile worst case (N = .01), a one-year sampling period, and both 10-day and one-day holding periods.

For purposes of this analysis, we compute the VaR of Aave v2. We expect this value to coincide up to two decimal places with the VaR of the entire Aave platform (v1 and v2), because Aave’s largest markets (including wBTC and ETH) are roughly 1000x larger in v2 than they are in v1.

### Model specifications

Gas prices are excluded from our calculations.

Any missing price change histories for newer tokens are proxied from Bitcoin price changes; although it’s not always a perfect proxy, the correlation to Bitcoin’s price changes is strong for most alt-coins. For example, below is a one-month trailing correlation of ETH and DOGE to BTC for the last quarter:

<img src="https://lh3.googleusercontent.com/uyj-ygoZRkHZhbFJ3P1JkOK5yQAYsXPhAlyil7ZURhd_E7amuX7c19tEWPBUZEFJ8nzxd8jQEcN53xtZTJRjzPv2mbZwDr-HE6LevKqbcReu5Zf9cLIm8Oi1K2Fx8xdoBNRVkw8" alt="" data-size="original">

### Historical VaR for Aave and Compound

To apply this model to Aave, we define the exposure as the total number of tokens borrowed less the total number of tokens deposited for each token available on the platform. **Deposits into Aave create an obligation for these deposits to be returned, in other words, a liability, and hence taken with a negative sign. Loans are the opposite, so taken with a positive sign.**

For example, if the total number of Yearn Finance (YFI) tokens deposited on Aave is 2,280, and the total borrowed is 597, we consider Aave’s position in YFI to be -1,613, i.e., 597 minus 2,280. The table below shows the net exposure of Aave and Compound as of 2 November 2021.



| **Token** | **Aave Position** | **Compound Position** |
| --------- | ----------------: | --------------------: |
| BTC       |           -18,630 |               -32,582 |
| ETH       |        -1,157,690 |            -1,573,250 |
| USDC      |      -280,000,000 |          -630,250,000 |
| USDT      |       -77,630,000 |          -107,940,000 |
| GUSD      |        -3,750,000 |                     - |
| SUSD      |       -15,160,000 |                     - |
| TUSD      |       -12,540,000 |           -14,260,000 |
| USDP      |        -8,240,000 |                     - |
| BAL       |          -421,000 |                     - |
| LINK      |       -19,681,680 |            -3,921,012 |
| MKR       |           -55,019 |                  -868 |
| RAI       |        -4,340,000 |                     - |
| UNI       |        -3,370,160 |                    -8 |
| SUSHI     |                 - |              -172,142 |
| XSUSHI    |        -9,190,000 |                     - |
| YFI       |            -1,613 |                   -63 |
| BUSD      |        -1,970,000 |                     - |
| FEI       |        -9,820,000 |                     - |
| FRAX      |        -2,050,000 |                     - |
| COMP      |                 - |              -459,415 |
| AAVE      |        -1,570,000 |               -14,586 |
| AMPL      |                 - |                     - |
| BAT       |        -4,601,880 |          -108,485,437 |
| CRV       |        -6,840,000 |                     - |
| DPI       |          -178,750 |                     - |
| ENJ       |       -10,125,660 |                     - |
| KNC       |          -686,700 |                     - |
| MANA      |       -13,140,000 |                     - |
| REN       |       -26,230,000 |                     - |
| RENFIL    |           -58,330 |                     - |
| SNX       |          -949,550 |                     - |
| ZRX       |        -1,180,590 |          -124,717,557 |
| SAI       |                 - |            -4,160,000 |
| DAI       |      -390,000,000 |          -752,600,000 |

Since all deposits exceed that of their respective total borrowed, both protocols hold a net short position in every token on their platform.

In this case, the 99% worst-case protocol-level VaR metrics are:



|            |      |          |            |
| ---------- | ---: | -------: | ---------: |
| In $ B.    | Aave | Compound | Difference |
| 1-day VaR  | 1.25 |     1.21 |      3.30% |
| 10-day VaR | 3.77 |     4.48 |     18.88% |

The 10-day VaR for Aave’s portfolio is $3.77B. It is smaller than Compound’s by 18.8% ($710M). The primary driver of such a big difference in VaR is that Compound has a higher net balance of ETH and BTC in its holdings, by 36 and 75 percent respectively. To understand how this plays out, let’s dig into the VaR computation.

### Computing and interpreting VaR

To compute the 10-day Var for either portfolio on Nov 2, 2021, we look back over the 10-day holding periods for the prior year, and organize them from worst to best for our current portfolio: the fourth worst scenario represents our VaR (one percent of 365 is about 4). The actual holding period that realizes this fourth-worst scenario will depend heavily on the portfolio. To see why this is true, think of a portfolio concentrated entirely in DOGE versus a portfolio concentrated entirely in BTC; we expect these portfolios to have different worst days in the previous year.

Even with such different portfolios, both Aave and Compound have their 10-day VaR realized over the same holding period: 30 December 2020 to 9 January 2021. This means the numerical value of 10-day VaR for both protocols are obtained by applying the percent changes in value of each token over the holding period 30 December – 9 January 2021. Below is the summary of changes for each token for this period

| **Token** | **30-Dec-20 to 9-Jan-21** |
| --------- | ------------------------: |
| BTC       |                       39% |
| ETH       |                       70% |
| USDC      |                        0% |
| USDT      |                        0% |
| GUSD      |                        0% |
| SUSD      |                       -4% |
| TUSD      |                        0% |
| USDP      |                        0% |
| BAL       |                       31% |
| LINK      |                       30% |
| MKR       |                       84% |
| RAI       |                       39% |
| UNI       |                       61% |
| SUSHI     |                       71% |
| XSUSHI    |                       39% |
| YFI       |                       56% |
| BUSD      |                        0% |
| FEI       |                       39% |
| FRAX      |                       -2% |
| COMP      |                       18% |
| AAVE      |                       42% |
| AMPL      |                        9% |
| BAT       |                       21% |
| CRV       |                       47% |
| DPI       |                       50% |
| ENJ       |                       64% |
| KNC       |                       39% |
| MANA      |                       55% |
| REN       |                        8% |
| RENFIL    |                      -15% |
| SNX       |                       51% |
| ZRX       |                       20% |
| SAI       |                       67% |
| DAI       |                       -1% |

&#x20;We apply these percent changes to the positions of Aave and Compound to obtain the loss in mark-to-market (MTM) for each token in both portfolios:

| **Token**               |                        **Aave** |                    **Compound** |
| ----------------------- | ------------------------------: | ------------------------------: |
| BTC                     |                     358,446,158 |                     626,886,352 |
| ETH                     |                   2,728,525,594 |                   3,707,946,765 |
| USDC                    |                        -840,084 |                       1,890,939 |
| USDT                    |                         248,391 |                         345,373 |
| GUSD                    |                         -11,602 |                             -   |
| SUSD                    |                        -536,977 |                             -   |
| TUSD                    |                         -36,253 |                         -41,225 |
| USDP                    |                         -18,948 |                             -   |
| BAL                     |                       3,013,571 |                             -   |
| LINK                    |                     161,450,379 |                      32,164,372 |
| MKR                     |                     116,951,443 |                       1,845,069 |
| RAI                     |                       5,173,210 |                             -   |
| UNI                     |                      53,254,891 |                             126 |
| SUSHI                   |                             -   |                       1,329,161 |
| XSUSHI                  |                      45,868,694 |                             -   |
| YFI                     |                      28,580,961 |                       1,116,305 |
| BUSD                    |                          -5,190 |                             -   |
| FEI                     |                       3,846,283 |                             -   |
| FRAX                    |                         -49,165 |                             -   |
| COMP                    |                             -   |                      27,272,921 |
| AAVE                    |                     204,803,796 |                       1,902,719 |
| BAT                     |                         716,222 |                      16,884,318 |
| CRV                     |                       9,042,931 |                             -   |
| DPI                     |                      30,592,891 |                             -   |
| ENJ                     |                      10,099,430 |                             -   |
| KNC                     |                         448,211 |                             -   |
| MANA                    |                       5,583,701 |                             -   |
| REN                     |                       2,487,422 |                             -   |
| RENFIL                  |                        -630,211 |                             -   |
| SNX                     |                       5,165,714 |                             -   |
| ZRX                     |                         231,740 |                      24,481,050 |
| SAI                     |                             -   |                      46,087,526 |
| DAI                     |                      -2,063,883 |                      -3,982,765 |
| **Total Loss in Value** |               **3,770,339,322** |               **4,482,347,128** |

&#x20;To see the role played by BTC and ETH, we consider a graphical representation:

![](https://lh5.googleusercontent.com/rxGEmWNws9YC-VtUzMJfT6NuQykSSVsvVG1Zh1UyrCrFUyQyUoe2EPR3RegtUMY-q0BDI4190fLfJFutr5g\_5gNSRuGZOzLELc1iMRGTAriAvGvxOaU1MVbkFEdU8KsZGXuhHbQ)

As can be seen, the majority of the VaR is driven by historically simulated loss in BTC and ETH, with Compound’s position more heavily concentrated in those markets.

1-day VaR estimates are relatively the same, Aave is at $1.25 B. and Compound at $1.21 B. To see this, we apply the same technique as above but with 1-day holding periods. This time the two portfolios have different days realizing their VaR: 5 February, 2021 for Aave and 3, May 2021 for Compound:

| **Token** | **5 Feb, 2021 (Aave)** | **3 May, 2021 (Compound)** |
| --------- | ---------------------: | -------------------------: |
| BTC       |                    18% |                        12% |
| ETH       |                     8% |                        16% |
| USDC      |                     0% |                         0% |
| USDT      |                     0% |                         0% |
| GUSD      |                    -3% |                         0% |
| SUSD      |                     1% |                         0% |
| TUSD      |                     0% |                         0% |
| USDP      |                    -1% |                         0% |
| BAL       |                    60% |                        12% |
| LINK      |                     3% |                        11% |
| MKR       |                    51% |                        20% |
| RAI       |                    18% |                         3% |
| UNI       |                    76% |                        23% |
| SUSHI     |                    99% |                        12% |
| XSUSHI    |                   107% |                        11% |
| YFI       |                     5% |                         6% |
| BUSD      |                    -1% |                         0% |
| FEI       |                    18% |                        10% |
| FRAX      |                    -2% |                         0% |
| COMP      |                   113% |                        51% |
| AAVE      |                    87% |                        32% |
| BAT       |                     4% |                        16% |
| CRV       |                    52% |                        17% |
| DPI       |                    58% |                        22% |
| ENJ       |                   -23% |                        18% |
| KNC       |                    18% |                        12% |
| MANA      |                     4% |                        12% |
| REN       |                    39% |                        19% |
| RENFIL    |                     0% |                        10% |
| SNX       |                    25% |                        12% |
| ZRX       |                    98% |                        24% |
| SAI       |                    19% |                        25% |
| DAI       |                     0% |                         1% |

&#x20;​​To compute the 1-day VaR, we apply these to each protocol’s 2 November, 2021 portfolio to obtain the Total Simulated Loss for each

| **Token**               | **Aave (5 Feb, 2021)** | **Compound (3 May, 2021)** |
| ----------------------- | ---------------------: | -------------------------: |
| BTC                     |            163,530,347 |                188,988,772 |
| ETH                     |            307,607,878 |                864,147,910 |
| USDC                    |                 28,017 |                     63,063 |
| USDT                    |                -31,027 |                    -10,788 |
| GUSD                    |               -118,799 |                          - |
| SUSD                    |                137,054 |                          - |
| TUSD                    |                 -7,449 |                    -45,618 |
| USDP                    |                -46,770 |                          - |
| BAL                     |              5,716,087 |                          - |
| LINK                    |             18,922,968 |                 12,248,425 |
| MKR                     |             71,686,404 |                    437,446 |
| RAI                     |              2,360,123 |                          - |
| UNI                     |             66,614,666 |                         48 |
| SUSHI                   |                      - |                    226,257 |
| XSUSHI                  |            125,746,986 |                          - |
| YFI                     |              2,757,772 |                    117,501 |
| BUSD                    |                -12,891 |                          - |
| FEI                     |              1,754,752 |                          - |
| FRAX                    |                -32,812 |                          - |
| COMP                    |                      - |                 77,203,936 |
| AAVE                    |            424,661,773 |                  1,474,580 |
| BAT                     |                121,131 |                 12,891,910 |
| CRV                     |              9,988,048 |                          - |
| DPI                     |             35,917,730 |                          - |
| ENJ                     |             -3,602,560 |                          - |
| KNC                     |                204,483 |                          - |
| MANA                    |                419,900 |                          - |
| REN                     |             12,438,939 |                          - |
| RENFIL                  |                 19,214 |                          - |
| SNX                     |              2,507,739 |                          - |
| ZRX                     |              1,158,592 |                 30,300,998 |
| SAI                     |                      - |                 17,219,266 |
| DAI                     |                467,626 |                  4,320,060 |
| **Total Loss in Value** |      **1,250,915,920** |          **1,209,583,767** |

Visualizing the data we see again that while BTC and ETH dominate the VaR for Compound, Aave’s VaR has more diverse contributions (including a large component coming from an almost overnight doubling of their token value):

![](https://lh4.googleusercontent.com/HzokJmaICikm8lgFKxXizyuYLvgQEuPrLtFwQeLG2257ghD\_dXDXvKwuGQex3fUo-G\_9SdrQj5fJb4xCJU9tsVc2J9XzLqX2drG0xWwis20E-ML0v2XfhuDGIkliBhTJpxTFOno)

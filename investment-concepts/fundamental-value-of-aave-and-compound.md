# Fundamental Value of Aave and Compound

## Executive Summary

Speculative activity can lead to significant under- or overpricing of assets compared to their intrinsic value. This is a problem. Another problem is the volatility of earnings and growth rates.

Given these, it is essential to understand the fundamental value of an investment. The below analysis is focused on estimating the intrinsic value of two DeFi lending protocols, Aave and Compound, by analyzing their net interest margin (NIM) over time as well as their discounted cash flows.

Based on our analysis, Aave is slightly overvalued, and Compound is undervalued.

## Net Interest Margin

For a lending protocol, the main stream of revenue is the interest received from borrowers and the main expense is interest paid to lenders. The net interest margin is defined as a measure of the difference between interest paid and interest received. NIM is the main indicator of profitability and growth of a financial organization. It should directly impact the value of equity and hence token price. The higher and more stable the NIM, the higher and more stable the fundamental value of the institution.

We have analyzed and compared the NIM-to-liabilities ratio of Aave and Compound over time.

As illustrated in the graph below, the NIM-to-liabilities ratio of Aave is more volatile than Compound's. The ratio for Aave varied in the past year from -0.10% to 0.50% with an average of 0.12%. Compound’s ratio moved from the low of 0.15% to the highest point of 0.37% with an average of 0.23%. This shows that Compound is almost twice as profitable as Aave.

Moreover, there appears to be a positive correlation between cryptocurrency market prices and the profitability ratio of both lending protocols. On the graph the pick of profitability for both protocols was at a peak of bullish sentiment for BTC (circled in red).

![NIM-to-Liabilities Ratio of Aave and Compound in Time](https://lh3.googleusercontent.com/zzj6IjwuRvhk1BuiUZRdkB3B\_QaZfIiXP0FEeeXLs8kfnUbXl8LO140JlQNHQ3WnXKprdKf1TDQxDLW4F8jWAYPJ5x3hcHzCe1lmATq3U7T6RYCUCfN5fOiY6LOD48e81GbHSpfVrDNE7VcR)

## Discounted Cash Flow Model

Derived profitability estimates can also be used to model the intrinsic value of the organization. One of these models is called the Discounted Cash Flow (DCF) model. DCF is a valuation method used to estimate the intrinsic value of an investment based on its expected future cash flows.

For the purposes of the current study we’ll consider two variations of the model, a two-stages growth model and a perpetual growth model.

### Two-stage Growth DCF Model

As its name indicates, the model is based on two stages. The first is the short-to-medium term when the growth is above normal. The second stage is when the company reaches maturity and grows at a long-term rate going forward.

In mathematical terms, the fundamental value of the company based on its cash flows (or dividends) could be expressed as:

![](<../.gitbook/assets/image (1).png>)

### Perpetual Growth DCF Model

The model is by far the most common due to its simplicity. It is used for investments with a solid history of dividend growth (blue chips), where it is reasonable to assume that the historical dividend growth rate will continue. The value of the organization is defined as:

![](<../.gitbook/assets/image (8).png>)

### Application

Assuming 5% as the required rate of return, and above-average growth lasting five years, we get the following results. The long-term growth rate is 3% \[1].

Net interest margin is assumed to be the only source of protocol revenue and is disseminated to token holders in full.

![](<../.gitbook/assets/image (9).png>)

On June 5th, Aave’s token is overpriced. It was trading at $200.63 even though its two-stage growth model net present value was $183.08 and its perpetual growth model net present value was at $87.49. Aave was experiencing significant growth in its balance sheet causing distortion in perpetual growth model valuation.

In contrast, Compound protocol token was underpriced. Its market price as of 5 June 2022 was $57.7 its intrinsic value, according to the two-stage growth model was $109.29, and its perpetual growth model net present value was $122.30. It must be mentioned that Compound balance sheet growth was, on average, slightly negative. For the valuation, it was assumed that deposits would remain constant before transitioning to long-term growth.

Historical data used to estimate the average margin and growth rate is listed in the Appendix.

## Conclusion

Analysis shows that Aave is over- and Compound is undervalued. Although some of the assumptions used might be improved further, they are consistent across both protocols, which supports comparability.

Aave’s cash flows are more volatile than Compound’s. The balance sheet growth of Aave is significantly higher. This might be an indication of a less conservative business model.

Profitability is an important factor, especially in the case of market stress, that we’re witnessing now in crypto market. Since all blockchain transactions are transparent, it provides an investment opportunity. Opportunity to value DeFi protocols on a trustless basis, monitor their performance going forward, and extract profit in case of mispricing.

## Appendix

Historical net interest margin data. Figures are annualized.&#x20;

**Aave**

![](https://lh3.googleusercontent.com/RcfO4fBx-5Zg6MpE\_ognWul-mIsnNrzvWoykAS-h-paGYNCTfXCwtqEVlKsTdR8swXkMA2ztVb3AEKyC3Rdf6\_tkPMGVX48-mD8ExsZ-tKImSjanxKvgmOu0tFBbCObEz4QghjypwEv\_-lON)

**Compound**

![](https://lh6.googleusercontent.com/vWg4\_SBdaFqqgTGgBw8MFywalwXsq4LDH-ziBNSKUcQL7XUf5cCEs57AE5\_gq3AvWBzWK3YtTsr7gpNLb4Z\_LCYlw\_3uQxq2U8xOrMh4bQgzNF7PAVd8ZrLZBMRHl6bSW\_-Q5bvLvnxz9XF6)

## References

1. Trading Economics, US GDP Growth Forecast https://tradingeconomics.com/united-states/gdp-growth-annual#:\~:text=GDP%20Annual%20Growth%20Rate%20in,the%20second%20quarter%20of%202020.

## **Version Control**

| **Version / Submission Date** | **Change Summary** | **Author(s) (Discord Handle, ETH Address, Reward)**                                         | **Reviewer(s) (Discord Handle, ETH Address, Reward)**                                                                                            |
| ----------------------------- | ------------------ | ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>1.0 / <br>29 June 2022</p> | Created            | <p>atulemis#0983,<br>0x5fb7584838fB467e90bb8a1df3a278482e34E856,</p><p>0 CMK (internal)</p> | <p>harri tarni,<br>0x295B61866dAA53a76CE4b3a927EFAF0059b4a90A,<br>0 CMK (internal)<br><br>matt | CMK#9019, mattropolis.eth, 0 CMK (internal)</p> |


# Market Risk

Value-at-Risk (VaR) is a model to measure market risk. VaR is a statistical measure of financial exposure. It is defined as the maximum dollar amount expected to be lost over a given time horizon, at a pre-defined confidence level, given normal market conditions.&#x20;

As an example, we computed the VaR for a theoretical holding of $1M worth of Ethereum (ETH).&#x20;

Based on 99% confidence level, 10-day holding period, and 1-year historical sampling window, the VaR of this position as of 6 October 2021 is equal to $379k. Table 3 shows other VaR estimates for other historical windows and holding periods.

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

The distribution in Figure 1 compares the VaR during a 10-day holding using data from the past year as well as all the historical data. The past year’s values are more skewed and platykurtic than the ones for the whole history.

![Figure 1 - Historical Distribution](https://lh4.googleusercontent.com/ScnxwOY4CALMglkTV05PbWf\_0LjBr5PXi4RiY\_TdbpUBH4b5w3kRvJJ\_Nx4nNAo6suBFaRxtxk38-JCGgnxhzSpU-6QlYKdazoGYnuipTNKBtfmC5u9f\_ybDS1\_v59APjvXaIRWQ)

These calculations exclude gas prices and transaction fees, which at times could exceed $5,000. We plan to compute the VaR for the protocols’ total portfolio.

### Summary&#x20;

Value at Risk (VaR) is used to measure the maximum potential loss caused by market movement under business-as-usual circumstances.&#x20;

Applied theoretically to ETH, both Aave and Compound have equal VaR. Future research will focus on applying VaR to Aave and Compound’s complete portfolios.

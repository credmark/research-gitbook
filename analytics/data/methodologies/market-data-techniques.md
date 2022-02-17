# Market Data Techniques

The on-chain market data is the raw and it needs to be checked and cleaned to be used for models. Below we describe the specifications.&#x20;

## Specification

* Input Time: given a period, i.e. min, sec, day, or OHLC (Open, High, Low, Close) versions of these periods, supply the series of price of a list of tokens. There is a global and per token setting for the day snapping time.
* Checks:
  * Missing
  * Staleness
  * Filtering by liquidity and tradeability: was any trade on this price? Is the trade volume sufficient for general liquidity?
  * Outlier detection
* Cleaning:
  * Missing data backfilling method: use previous data point, or proxy choice
  * Alignment: use the last available data point, or using missing data backfilling method
  * Outlier removal or keep (dangerous)

## Contributors <a href="#contributors" id="contributors"></a>

| Discord Handle | ETH address                                 | Reward          | Contribution     |
| -------------- | ------------------------------------------- | --------------- | ---------------- |
| ​kunlun#8324   | 0x109B3C39d675A2FF16354E116d080B94d238a7c90 | $CMK (internal) | Original version |

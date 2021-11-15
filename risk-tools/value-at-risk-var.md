# Value at Risk (VAR)

Value-at-Risk (VaR) is a model to measure market risk. VaR is a statistical measure used to calculate the maximum potential loss caused by market movement under business-as-usual circumstances. It is defined as the maximum dollar amount expected to be lost over a given time horizon, at a pre-defined confidence level, given normal market conditions. It’s important to note that this measure doesn’t provide any guidance on how much can be lost in a “black swan” type event.

VaR is commonly used in TradFi to calculate potential losses. By aggregating portfolio level VaRs organizations can understand the maximum potential organizational losses and take a quantitative decision on risk, either by increasing capital reserves or moving into lower-VaR positions.

Because VaR is applicable to any group that holds assets subject to market fluctuations, it can easily, and usefully, be applied to Crypto as a financial primitive.

There are three primary types of VaR modelling: the historical, the variance-covariance method and the Monte Carlo simulation.

For simplicity, below is the formula for the Historical 10-day VaR of the Trading book based on the last year sampling.

****

**CALCULATION:**

![](<../.gitbook/assets/VAR calculation.png>)

where:&#x20;

Lossn - portfolio loss for on the observation date n; m - the number of crypto assets in the trading book;&#x20;

n - the observation number applied retrospectively, for example 30th of June 2021 is n and n+1 is 29th of June 2021;&#x20;

Xm - the quantity of the asset m in the book;&#x20;

Pmn - price of the asset m at the observation n date;&#x20;

Base case - the reporting date, or yesterday.

Note that a negative Lossn entails a profit. Then the 99% worst case 10-day VaR could be determined as the 4th largest loss.

****

**DATA NEEDED & CONSIDERATIONS:**&#x20;

VaR calculation is based on two types of data: Current exposure, which is simply list of assets and their quantities in the portfolio Histories of the prices of those assets

There are several ways to go about calculating VaR. The first is by looking at historical data. This method assumes that the past will inform the future and looks retroactively at market movement. For example, you could look at the past year’s worth of data on market movement, identify the highest market movement for a period of time (i.e. 1 day, 10 day, 30 day) and apply them to current holdings.

A second methodology utilizes the standard deviation and correlations of assets- in other words the potential losses are assumed to be normally distributed and applied against the mean price of an asset with calculated correlations.

Lastly, complex simulations can be built to calculate potential gains, losses and their likelihood of occurring based on anticipated behaviour

While VaR can be a useful tool, it is important to consider its limitations. Because VaR often relies on historical data it can be a poor predictor of edge-case, or extreme market fluctuations.

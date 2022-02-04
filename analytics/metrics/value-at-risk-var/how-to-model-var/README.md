# How to model VaR?

There are three primary types of VaR modeling: the historical, the variance-covariance method and the Monte Carlo simulation.

For simplicity, below is the formula for the Historical 10-day VaR of the Trading book based on the last year sampling.

****

**CALCULATION:**

$$
{PPL}_n = \sum_{m=1}^{M}\left (  X_m \times P_m^{\text{base case}} \times {R}_{m,n} \right ), n=1,...,365
$$



$$
{VaR}_{1-\alpha}({PPL}) = - \left \{ t: Pr \left ( {{PPL} \le t} \right ) \ge \alpha \right \}
$$

where:&#x20;

* $${PPL}_n$$: potential profit or loss of a portfolio on the observation date n;
* $$m$$: the number of crypto assets in the trading book;
* $$n$$: the observation number applied retrospectively, for example, 30th of June 2021 is n and n+1 is 29th of June 2021;
* $$X_m$$: the quantity of the asset $$m$$ in the book;&#x20;
* $$\text{Base case}$$: the reporting date;
* $$P_{m}^{\text{base case}}$$: price of the asset m at the base case date;
* $$R_{m,n}$$: Return of the asset $$m$$ during the period of observation days $$n$$;
* $${Pr}$$: Probability function;
* $$1-\alpha$$: confidence level.

$${VaR}_{1-\alpha}$$ is the $$\alpha$$-quantile of $${PPL}$$ vector.

Note that a negative $${PPL}_n$$entails a loss. Then the 99% worst case 10-day VaR with 365 scenarios could be determined as negated weighted average between 4th and 5th largest loss.

****

**DATA NEEDED & CONSIDERATIONS:**&#x20;

VaR calculation is based on two types of data: Current exposure, which is simply list of assets and their quantities in the portfolio Histories of the prices of those assets

There are several ways to go about calculating VaR. The first is by looking at historical data. This method assumes that the past will inform the future and looks retroactively at market movement. For example, you could look at the past year’s worth of data on market movement, identify the highest market movement for a period of time (i.e. 1 day, 10 day, 30 day) and apply them to current holdings.

A second methodology utilizes the standard deviation and correlations of assets- in other words the potential losses are assumed to be normally distributed and applied against the mean price of an asset with calculated correlations.

Lastly, complex simulations can be built to calculate potential gains, losses, and likelihood of occurring based on anticipated behavior.

While VaR can be a useful tool, it is important to consider its limitations. Because VaR often relies on historical data it can be a poor predictor of edge-case, or extreme market fluctuations.

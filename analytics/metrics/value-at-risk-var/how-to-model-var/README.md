# How to model VaR?

There are three primary types of VaR modeling: the parametric method (also known as variance-covariance method), and simulation-based methods, such as historical VaR simulation, and Monte-Carlo simulation.

## Data Required

VaR calculation is based on two types of data:

* Exposures, which is can be simply list of assets and their quantities, or derivatives contracts in the portfolio
* Histories of the prices of those assets

## Methodology

There are several ways to go about calculating VaR.

* The parametric VaR method utilizes the standard deviation and correlations of assets, forming the covariance matrix. In other words the potential losses are assumed to be normally distributed and applied against the mean price of an asset with calculated correlations. The covariance matrix can be generated from historical data and designated scenarios.
* The simulation-based VaR methods is based on scenarios that describe the market movements, such as ETHUSD moved +5% while BTCUSD moved -5%. The scenario is applied to the base market and the portfolio is re-evaluated with the changed market. The change of the value of the portfolio is measured as PnL (profit and loss) impact from the scenario.
  * The first simulation-based method is to use the historical scenarios to perform simulation. This method assumes that the past event/market moves will repeat in the future as a plausible scenario and looks retroactively at market movement. For example, you could look at the past year’s worth of data on market movement, create scenarios based on the market movement for a period of time (i.e. 1 day, 10 day, 30 day) and apply them to current holdings as a simulation.
  * The second simulation-based method is to employ complex and computationally-intensive Monte Carlo based-simulations to calculate potential gains, losses, and likelihood of occurring based on anticipated behavior.

## Considerations

While VaR can be a useful tool, it is important to consider its limitations.

* Because VaR often relies on historical data it can be a poor predictor of edge-case, or extreme market fluctuations. Historical data quality issues (wrong, missing, staled, misalignment due to different snapping or market closing time) could result in poor performance of VaR models.
* Different VaR methods has various assumptions to the underlying distribution of the market move which is a theoretical overlay to the market reality. Parametric method has the assumptions of normal distribution of the returns and therefore suffered most from this limitation.
  * Historical scenarios does not assume the distribution but the selected historical period may not contain sufficient number of the stress events. Monte-Carlo based simulation can be designed to sample normal distribution with designated covariance matrix to mitigate for this limitation.
* VaR is calculated based on the positions in the portfolio at a time of snapping. If there is many intra-day trading activities and market movements, VaR model is not sufficient to estimate the risk. Increasing the frequency of the calculation with position and market updates will be necessary.
* The parametric VaR can only evaluate linear exposures' change of value, lacking of support of change from high-order risk factor change. The simulation-based VaR methods have a choice of using approximated re-valuation or full-revaluation based on pricing model so the performance of such VaR models is better while being more computational intensive.
* Backtesting of the VaR model is an integral part of the VaR model. The limitations described above would be tested in real world performance of the VaR model in terms of the magnitude and number of exceptions of Hypothetical PnL ("Hypo PnL") is more than what VaR model estimates. The downside risk of Hypo PnL is more negative than the VaR needs to be investigated thoroughly to attribute to reasons.

## VaR Calculation

### Parametric VaR method

$$VaR$$ is a function of the standard deviation $$\sigma$$, the z-score on the desired confidence level $$z_p$$ and the present value of the portfolio $$PV$$.

$$
VaR=z_p \cdot \sigma \cdot PV
$$

For a portfolio of assets, we can combine $$\sigma$$ and $$PV$$with below formula. $$\Sigma$$ is the covariance matrix of the $$n$$ assets.

$$
(\sigma \cdot PV)^2 = \left [ v_1, \cdots, v_n  \right ] \begin{bmatrix}
\sigma_{11} & \cdots  & \sigma_{1n}\\ 
\vdots &  & \vdots \\ 
\sigma_{n1} & \cdots & \sigma_{nn}
\end{bmatrix} \begin{bmatrix}
v_1\\ 
\vdots \\ 
v_n
\end{bmatrix} = v ^ \prime \Sigma v
$$

### Simulation-based method

We calculate VaR from the $$PPL$$ vector.

$$
{VaR}_{1-\alpha}({PPL}) = - \left \{ t: Pr \left ( {{PPL} \le t} \right ) \ge \alpha \right \}
$$

where:

* $$PPL$$: a vector of potential profit and loss from VaR simulations. The single value is calculated as the change in $$Value$$ from market changes&#x20;
* $$Pr$$: Probability function
* $$\alpha$$: confidence level.

Mathematically, $$VaR$$ is the $$\alpha$$-quantile of vector of $$PPL$$. The VaR at level $$\alpha \in (0,1)$$ is the smallest number $$y$$ such that the probability $$Y:=-X$$ does not exceed $$y$$ is at least $$\alpha$$.

#### 1. Historical VaR Simulation

For simplicity, below is the formula for the Historical 10-day VaR of the Trading book based on the last year sampling.

$$
{PPL}_n = \sum_{m=1}^{M}\left (  X_m \times P_m^{\text{base case}} \times {R}_{m,n} \right ), n=1,...,365
$$

where:

* $${PPL}_n$$: potential profit or loss of a portfolio on the observation date $$n$$;
* $$m$$: the number of crypto assets in the trading book;
* $$n$$: the observation number applied retrospectively, for example, 30th of June 2021 is $$n$$ and $$n+1$$ is 29th of June 2021;
* $$X_m$$: the quantity of the asset in the book;
* $$\text{base case}$$ : the reporting date;
* $$P_m^{\text{base case}}$$: price of the asset m at the base case date;
* $$R_{m,n}$$: Return of the asset during the period of observation days ;

Note that a negative entails a loss. Then the 99% worst case 10-day VaR with 365 scenarios could be determined as negated weighted average between 4th and 5th largest loss.

#### 2. Monte-Carlo VaR Simulation

The Monte-Carlo VaR simulation differs from Historical VaR simulation by how the scenarios are generated. Instead of historical scenarios, the scenario of asset returns are generated from the covariance matrix calculated from the historical data (more to be found in [correlation-covariance-matrix.md](../../../data/modeling/correlation-covariance-matrix.md "mention")). With covariance matrix $$C$$, we can decompose it and form the transformation matrix $$L$$.

$$
C = LL^T
$$

The correlated random number $$R^\prime$$ can be obtained from uncorrelated ranom number $$R$$ by

$$
R^\prime=LR
$$



The correlated random number $$R ^ \prime$$ can be used as scenarios of market movements. The rest of the model on consuming the data and calculate the $$PPL$$ is the same.

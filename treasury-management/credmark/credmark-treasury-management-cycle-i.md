# Credmark Treasury Management Cycle I



### Cycle <a href="#_zaomtcf27tzy" id="_zaomtcf27tzy"></a>

| **Deployment Date** | TBD     |
| ------------------- | ------- |
| **Cycle Length**    | 30 days |

### Capital Allocation <a href="#_fqyj7jqixk5i" id="_fqyj7jqixk5i"></a>

| **TOTAL (USD)** | 1,000,000 |
| --------------- | --------- |
| **Low Risk**    | 700,000   |
| **Medium Risk** | 200,000   |
| **High Risk**   | 100,000   |

### Risk and Yield Parameters <a href="#_avrcu7478s2b" id="_avrcu7478s2b"></a>

|                 | **Max VaR (Annual)** | **Yield Target (Annual)** |
| --------------- | -------------------- | ------------------------- |
| **Low Risk**    | 1.5%                 | 3%                        |
| **Medium Risk** | 10%                  | 20%                       |
| **High Risk**   | 25%                  | 50%                       |

### &#x20;<a href="#_g2ms1hx1nb8y" id="_g2ms1hx1nb8y"></a>

### Allocation <a href="#_uz57cfvnab2h" id="_uz57cfvnab2h"></a>

### Goal <a href="#_k9jbxyr31aqg" id="_k9jbxyr31aqg"></a>

For this first cycle we decided to keep things simple!

We only planned 3 activities:

1. Lending.
2. Holding volatile assets.
3. Providing liquidity to DEXes.

We chose these because we could:

1. easily compute the VaR on a portfolio basis using historical data, and
2. estimate yields based on current market conditions.

### Details <a href="#_1ffq5a9ad5p2" id="_1ffq5a9ad5p2"></a>

| **Risk Profile** | **Capital Allocation** |               |
| ---------------- | ---------------------- | ------------- |
|                  |                        |               |
| **Target**       | **Actual**             |               |
| Low              | 700,000                | 700,000       |
| Med              | 200,000                | 230,000       |
| High             | 100,000                | 70,000        |
| **TOTAL**        | **1,000,000**          | **1,000,000** |

| **Risk Profile** | **VaR**       |            |           |
| ---------------- | ------------- | ---------- | --------- |
| **Target**       | **Projected** | **Diff**   |           |
| Low              | 1.5%          | 0.74%      | -0.76%    |
| Med              | 10.0%         | 47.61%     | 37.61%    |
| High             | 25.0%         | 52.96%     | 27.96%    |
| **Weighted AVG** | **10.2%**     | **15.18%** | **4.98%** |

| **Risk Profile** | <p><strong>Yield</strong></p><p>(Annual)</p> |            |            |
| ---------------- | -------------------------------------------- | ---------- | ---------- |
| **Target**       | **Projected**                                | **Diff**   |            |
| Low              | 3.0%                                         | 3.26%      | 0.26%      |
| Med              | 20.0%                                        | 42.29%     | 22.29%     |
| High             | 50.0%                                        | 70.26%     | 20.26%     |
| **Weighted AVG** | **10.2%**                                    | **15.26%** | **5.06%.** |

| **Risk Profile** | <p><strong>Yield</strong></p><p>(Cycle)</p> |             |            |
| ---------------- | ------------------------------------------- | ----------- | ---------- |
| **Target**       | **Projected**                               | **Diff**    |            |
| Low              | $1,726                                      | $1,873      | $147       |
| Med              | $3,521                                      | $6,861      | $3,340     |
| High             | $2,406                                      | $3,174      | $768       |
| **TOTAL**        | **$7,653**                                  | **$11,908** | **$4,255** |

### Commentary <a href="#_p5bgmpi635fs" id="_p5bgmpi635fs"></a>

#### Asset Diversification <a href="#_oop4byyq8w6q" id="_oop4byyq8w6q"></a>

As part of this cycle we diversified $3,000,000 worth of treasury assets. This was intended to address concentration, protocol, and regulatory risks. It also sets aside tokens to cover transaction fees. This diversification has no material impact on the treasury management overall.

This is a summary of our closing positions:

| **Type**   | **Asset** | **Proportion** | **Value**      |
| ---------- | --------- | -------------- | -------------- |
| Stablecoin | USDT      | 20%            | **$600,000**   |
| Stablecoin | USDC      | 20%            | **$600,000**   |
| Stablecoin | TUSD      | 9%             | **$270,000**   |
| Stablecoin | DAI       | 20%            | **$600,000**   |
| Stablecoin | PAX       | 7%             | **$210,000**   |
| Gas        | MATIC     | 1%             | **$30,000**    |
| Gas        | Solana    | 1%             | **$30,000**    |
| Gas        | ADA       | 1%             | **$30,000**    |
| Gas        | ETH       | 6%             | **$180,000**   |
| Fiat       | USD       | 15%            | **$450,000**   |
| **TOTAL**  |           | **100%**       | **$3,000,000** |

#### VaR <a href="#_ixutlya6fted" id="_ixutlya6fted"></a>

All VaR figures were computed on a portfolio basis using one year of historical data. When an asset or position didn’t exist for that full period, we used proxies. All of the historical data used to compute our VaR figures can be found [here](https://docs.google.com/spreadsheets/d/1qPPGzU2kqklozpK7rPRDpjpnanbIpJ4Uwj\_0eq8CypI/edit?usp=sharing).

The obvious thing to note in the tables above is how much more risk we were willing to take compared to the target. We discussed this at length.

We believe that our computed VaR values are greatly exaggerated. We used a year’s worth of historical data because that would be the norm in traditional finance. Traditional finance, however, doesn’t deal with the level of volatility we see in crypto. As an example, ETH increased in value 20x over the course of the year.

We considered shortening the historical data period but realized that it would not be conservative enough. In future we will likely move away from computing VaR using this technique.

#### Yield <a href="#_ufietzzec67z" id="_ufietzzec67z"></a>

We are projecting significantly greater yield from our medium and high risk positions than our stated targets. This is because markets are relatively frothy at the start of this cycle. Any downturn will bring us closer in line with our targets.

In future we will likely adjust yield projections using historical data.

#### Investment Positions <a href="#_rk91cms8znbx" id="_rk91cms8znbx"></a>

Investment position details can be found [here](https://docs.google.com/spreadsheets/d/16spAVgFh4GFzZZyA4dYPiyWWrwxPiBHBjz2fG\_mhLMQ/edit?usp=sharing) in the “Investment Strategy” tab. Some of our decisions are likely to raise eyebrows. For example, why would we provide ETH/BTC liquidity if our projected annual return is 15% while our VaR is 79%? We reviewed the historical data and we believe the computed VaR is far too high given recent market conditions. We also believe that potential returns are significantly higher.

Looking at the “APR Source” column in the “Investment Strategy” tab, you’ll notice that “Research” is used for about a third of the positions. More information can be found in the “Investment Rationale” tab, but we have to confess that some of those values are the result of “educated guesses” after spending time with a variety of investment tools. We expect to provide more rigorous analysis in the future.

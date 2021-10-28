# Liquidity Risk

Liquidity risk is the risk that a business will have insufficient funds to meet its financial commitments in a timely manner.&#x20;

To measure this risk, we use a metric called liquidity coverage ratio (LCR). LCR is defined as the proportion of highly liquid assets held by an organization to ensure that they maintain an ongoing ability to meet their short-term obligations (cash outflows for 30 days) in a stress situation. It is one of the essential liquidity risk measures in traditional finance. The mathematical formula is:

![](<../../../.gitbook/assets/Screen Shot 2021-10-28 at 2.34.50 PM.png>)

**Net cash outflows – **net outflows from depositors removing funds and early loans liquidations under stress.

**Liquidity buffer – **the funds held in the safety module for each protocol.

Aave and Compound have similar business models. They borrow funds from depositors and lend these funds at a higher rate. This margin is then distributed to the token holders.

Most of the funds collected from the sale of tokens are held in a diversified portfolio of highly liquid cryptocurrencies and act as a buffer for contingent liabilities. This buffer is often called a 'Safety Module'. Except for 'Safety Module' liquidity, the protocol can raise money through additional token issuances. However, this option is less favorable due to its negative effect on token price in a stress situation.

To parameterize LCR, we came up with the following assumptions on the stress scenario**:**

* High net worth individuals and wholesale clients withdraw their funds, representing 20% of the total deposit portfolio.
* Observed market volatility results in a 10% net loss in volatility-triggered liquidations.
* The safety module is down by 30% due to a market crash and subsequent sell-off of the native token.

Table 4 lists a comparative analysis of Aave2 and Compound protocol LCR with the breakdown of its components. Aave2 LCR is assumed to be the same for all Aave protocols.

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |
|   |   |   |

Aave has an LCR 42.03%, which is 6.23% higher than Compound’s. Aave’s liquidity management is clearly more robust than Compound’s. This is primarily explained by Aave’s Safety Module being 37% higher than Compound’s.&#x20;

Credmark is continuing to refine the LCR framework and investigating ways to monitor the metric in real time.

### Summary

&#x20;Liquidity Coverage Ratio is used to assess how well a protocol could mitigate a scenario where more money is owed to borrowers than collateral held by the platform. Aave outperforms Compound because they hold more money in their Safety Module proportionate to money withdrawn by borrowers.

****

# FRAX

FRAX is an algorithmic stable coin pegged to the US dollar, partially backed by collateral (or “fractional-algorithmic”). The FRAX token is part of the FRAX Finance ecosystem, whose native governance token is FXS (“FRAX shares”).

## Collateral Ratio (CR)

The FRAX stable coin is backed both by collateral (USDC) and by the value of the Frax governance token FXS. The protocol contains a parameter $$C_r$$ (between 0 and 1) representing the percentage of collateral value required to mint new FRAX tokens, and the (complementary) percentage of FXS required to be burned to mint new FRAX tokens. As of June 14, 2022 $$C_r = 89.5$$​.

### Minting FRAX

To mint a single FRAX token, one supplies $$C_r$$ worth of collateral and burns $$1-C_r$$ worth of FXS tokens. More generally, to mint $$F$$ FRAX tokens using USDC as collateral (assuming USDC/dollar = 1) when the price of FXS is $$P$$ dollars, one must supply $$F \cdot C_r$$ in collateral and burn $$(1-C_r) \cdot \frac{F}{P}$$ FXS tokens.

Minting FRAX is only permitted when the price of FRAX is above $1 (US).

### Edge Cases for CR

When the parameter $$C_r = 1$$, it costs exactly $1 of collateral to mint a single FRAX token (excluding any gas and fees). At this end of the interval, FRAX is fully collateralized; think “DAI stablecoin and MKR governance token”.

When the parameter $$C_r = 0$$, one must burn exactly $1 worth of FXS tokens to mint a single FRAX token (excluding any gas and fees). At this end of the interval, FRAX is fully algorithmic using the value of the FXS token; think “UST stablecoin and Luna governance token”.

### Redeeming FRAX

The variable $$C_r$$ also determines how FRAX tokens are redeemed. No matter when the specific token in question was minted, when it is submitted for redemption the protocol returns $$C_r$$ collateral and $$1-C_r$$ dollars worth of minted FXS.

Redeeming FRAX is only permitted when the price of FRAX is below $1 (US).

### Price Stability

When $$C_r = 1$$, the price of FRAX is as stable as its collateral.

When $$C_r < 1$$, and the price of FXS is greater than 0, there is an arbitrage opportunity created whenever the price of FRAX moves above or below $1. When FRAX is priced above $1, one can mint FRAX for $1 worth of collateral and FXS, and then sell the newly minted FRAX for the higher price. This arbitrage opportunity exists until Frax is priced at $1 again. When the price of FRAX moves below $1, one can purchase FRAX for the lower price and redeem it for $1 worth of collateral and FXS.&#x20;

**Modeling Question:** we know these stabilizing forces failed to prevent price depegging in the case of UST/LUNA. For a given value of $$C_r$$, how is FRAX price volatility impacted by this arbitrage? How does this depend on liquidity of FXS and volume of minting/redeeming of FRAX?

## Algorithmic Market Operations (AMOs)

Given enough time and volume, the arbitrage mechanism described in [#price-stability](frax.md#price-stability "mention") will stabilize the price of FRAX to $1 US. How much time and volume are available depends strongly on the liquidity of FXS, and the FRAX protocol has developed mechanisms to automatically control the available to liquidity of FXS.

### Dynamically adjusted $$C_r$$

The FRAX docs describe a way to compare FXS liquidity to total supply of FRAX tokens called the [PIDController](https://docs.frax.finance/amo/fxs1559). First they describe an approximation of FXS liquidity, and then take the ratio of this approximation and total supply of FRAX tokens.

If the PIDController is increasing, then there is more FXS liquidity available relative to total supply of FRAX. This increased available value from FXS implies that $$C_r$$ can be decreased (ie, FRAX value can lean more on FXS value rather than collateral) without impacting the solvency of the protocol. When $$C_r$$ is decreased, it contributes negatively to the rate of change of the PIDController. Another way to say this is that when $$C_r$$ is decreased, it slows down the PIDController increase, possibly stopping its movement altogether or reversing its direction.

If the PIDController is decreasing, there is less available FXS liquidity relative to total supply of FRAX, and increasing $$C_r$$​ may be required to maintain protocol solvency. When $$C_r$$​ is increased, it contributes positively to the rate of change of the PID controller, slowing down its decrease and possibly stopping its movement altogether or reversing its direction.

In both cases, the impact of $$C_r$$​ on $$\textrm{PIDController}$$ depends on volume of FRAX minting/redemption.

**Modeling Question:** What is the impact of $$\Delta C_r$$​ on $$\Delta \textrm{PIDController}$$? How does this depend on: volume of minting/redemption, $$C_r$$, $$\textrm{PIDController}$$?

**Modeling Question**: Compare the approximation of FXS liquidity to the actual liquidity of the FXS token. What can we say about the difference, and how does it impact the PIDController strategy?

**Modeling Question:** How does $$\Delta C_r$$​impact FXS liquidity? How does this depend on volume of minting/redemption?

### The basic AMO

The FRAX protocol's parameter $$C_r$$​ is automatically adjusted in response to PIDController movement.

1. When PIDController is increasing, $$C_r$$​ is decreased.
2. If the PIDController is not moving (enough),  $$C_r$$​ remains unchanged.
3. When PIDController is decreasing, $$C_r$$​ is increased.
4. As the FRAX protocol accrues collateral in excess of $$\textrm{Total Supply of Frax} * C_r$$, these additional funds are used to mint an equivalent amount of FRAX, which are then used to purchase FXS on AMMs, which are then burned. This mechanism is designed to move (per capita) value of FRAX above $1 to the FXS token.

**Modeling Question:** How do FRAX's fees for minting/redeeming impact earlier models?&#x20;

**Modeling Question:** Are protocol fees the main mechanism by which FRAX protocol accrues value in excess of $$\textrm{Total Supply of Frax} * C_r$$? ​

### More general AMOs

FRAX protocol allows for the creation of independent smart contracts that act in a similar way to the basic AMO. They are required to have the [following specifications](https://docs.frax.finance/amo/overview):

1. Decollateralize - some smart market actions that users can activate that impacts the $$C_r$$ by lowering it. The FRAX [documentation](https://docs.frax.finance/amo/overview) still mentions this is only permitted when the price of FRAX is above $1, but we wonder whether newer permissions consider PIDController instead.
2. Equilibrium - market actions that do not impact $$C_r$$.
3. Recollateralize - some market actions that users can activate that impacts $$C_r$$​ by raising it. There is mention of permissions depending on price of FRAX falling below $1, but we wonder whether this is permissioned by the PIDController.
4. FXS Value Accrual Mechanism - a formal accounting of the additional value of the AMO, and a strategy for using that excess value to acquire and burn an equivalent amount of FXS (thereby transferring the excess value to the FXS token)

The following examples of AMOs are referenced in the FRAX documentation.&#x20;

#### [Collateral Investor](https://docs.frax.finance/amo/collateral-investor) AMO

#### [Curve](https://docs.frax.finance/amo/curve) AMO

#### [Uniswap v3](https://docs.frax.finance/amo/uniswap-v3) AMO

#### [Collateral Hedge](https://docs.frax.finance/amo/collateral-hedge) AMO

#### [FRAX Lending](https://docs.frax.finance/amo/frax-lending) AMO

## PIDController and FRAX Protocol Solvency

In order for FRAX to maintain its peg, the FRAX protocol must be able to redeem each FRAX token for $$C_r$$​ USDC and $$(1-C_r)$$​ dollars worth of FXS. This means that in order for the FRAX protocol to be solvent, there are two distinct requirements:

1. For each FRAX  token that could possibly be redeemed, FRAX protocol must have $$C_r$$​ liquid USDC. Overall, this means FRAX protocol must have access to $$\textrm{totalRedeemableFRAX} * C_r$$​ liquid USDC.
2. For each FRAX token that could possibly be redeemed, there must be $$(1-C_r)$$ USD of extractable value in FXS token markets. This means that the FXS market must have $$\textrm{totalRedeemableFRAX} * (1-C_r)$$​ of reliably extractable USD. Moreover, this value must be reliably extracted by $$\frac{\textrm{totalRedeemableFRAX} * (1-C_r)}{\textrm{priceFXS}}$$ FXS tokens, as this is the amount of FXS the FRAX protocol will return if all redeemable FRAX is redeemed.

The first requirement is a familiar problem from traditional finance and treasury risk management: "If X is the total amount of liquid USDC we need in the worst case, how much do we need to actually keep in hand?"&#x20;

In the next sections, we'll analyze the second requirement against the FRAX protocol structure.

### Definitions

In [Dynamically Adjusted](frax.md#dynamically-adjusted) $$C_r$$, we described the PIDController as the ratio of an approximation of FXS liquidity to the total supply of FRAX tokens. This measure is intended to approximate how solvent FRAX protocol is with respect to Requirement 2.&#x20;

A more precise definition is $${ \textrm{PIDController}(t) = \frac{\displaystyle   \sum_{\textrm{pair markets } FXS:TKN} \textrm{Price}(FXS, TKN, t) \cdot \textrm{Supply}(FXS,TKN, t)}{\displaystyle   \textrm{totalFRAXSsupply}(t)}}$$The approximation used here for FXS liquidity is market-cap​, which is known to overestimate liquidity as it assumes every token can be sold for the current price, rather than taking slippage into account (as more tokens sell, the price drops).

We define another invariant, which we call the solvencyController, as follows

$${\textrm{solvencyController}(t) = \frac{\displaystyle \sum_{\textrm{pair markets } FXS:TKN} \textrm{totalUSDExtractable}(FXS, TKN,t)}{\displaystyle \textrm{totalFRAXSsupply}(t)}}$$​This measure by definition includes slippage in the calculation of liquidity, and so is a precise measure of the ratio of extractable dollars in FXS market to total FRAX supply.

Both of these measures change with time, and we include that parameter in the definitions.

### Analysis

#### Solvency is measured by the solvencyController

We give the solvencyController it's name because for a given value of $$C_r$$​, the FRAX protocol is solvent in the sense of Requirement 2 (able to fund the FXS portion of arbitrage redemption of all redeemable FRAX tokens) if and only if the following equation holds:&#x20;

$$\displaystyle \textrm{solvencyController}(t) \geq (1-C_r)$$.

#### Relationship between PIDController and solvencyController

Because market cap is always an overestimate of extractable dollar value (because it ignores slippage), we have the following relationship between the PIDController and solvencyController:

$$\displaystyle \textrm{PIDController}(t) \geq \textrm{solvencyController}(t)$$.

#### Possible exposure to FXS insolvency​

Because the PIDController is the primary invariant controller the movement of $$C_r$$​, and because it is always greater than the solvencyController, the door is open for the following situation:

$$\textrm{PIDController}(t) \geq 1 - C_r > \textrm{solvencyController}(t)$$.

What this means is that the PIDController can indicate "everything is good, we are totally solvent" while in fact the protocol is insolvent when accounting for slippage. In this situation, the PIDController may even move $$C_r$$ so that the FRAX protocol leans more heavily on an already insufficient FXS liquidity.

**Modeling Questions:**&#x20;

1. How do PIDController and solvencyController relate to each other historically?&#x20;
2. How do PIDController and solvencyController compare to $$(1-C_r)$$​ historically? In particular, have either of these measures ever disagreed about whether FRAX protocol was solvent with respect to Requirement 2?
3. How do the calculations in our analysis change when $$C_r$$​ is not fixed (as we assumed at the start), but adjusting dynamically in response to the PIDController?
4. How do the calculations in our analysis change if instead $$C_r$$ were adjusting dynamically in response to solvencyController rather than PIDController?
5. Can we describe market conditions that would lead to the risk regime $$\textrm{PIDController}(t) \geq 1 - C_r > \textrm{solvencyController}(t)$$?
6. If the protocol dynamically adjusted $$C_r$$ by solvencyController rather than PIDController, how would the protocol respond to the market conditions discovered in Modeling Question 5?&#x20;

#### Token:

{% embed url="https://etherscan.io/token/0x853d955acef822db058eb8505911ed77f175b99e" %}

**Contract:**

{% embed url="https://etherscan.io/address/0x853d955acef822db058eb8505911ed77f175b99e#code" %}

# FRAX

FRAX is an algorithmic stable coin pegged to the US dollar, partially backed by collateral (or “fractional-algorithmic”). The FRAX token is part of the FRAX Finance ecosystem, whose native governance token is FXS (“FRAX shares”).

## Collateral Ratio (CR)

The FRAX stable coin is backed both by collateral (mostly USDC) and by the value of the Frax governance token FXS. contains a parameter $$C_r$$ (between 0 and 1) representing the percentage of collateral value required to mint new FRAX tokens, and the (complementary) percentage of FXS required to be burned to mind new FRAX tokens. As of June 14, 2022 $$C_r = 89.5$$​.

### Minting FRAX

To mint a single FRAX token, one supplies $$C_r$$ worth of collateral and burns $$1-C_r$$ worth of FXS tokens. More generally, to mint $$F$$ FRAX tokens using USDC as collateral (assuming USDC/dollar = 1) when the price of FXS is $$P$$ dollars, one must supply $$F \cdot C_r$$ in collateral and burn $$(1-C_r) \cdot \frac{F}{P}$$ FXS tokens.

### Edge Cases for CR

When the parameter $$C_r = 1$$, it costs exactly $1 of collateral to mint a single FRAX token (excluding any gas and fees). At this end of the interval, FRAX is fully collateralized; think “DAI stablecoin and MKR governance token”.

When the parameter $$C_r = 0$$, one must burn exactly $1 worth of FXS tokens to mint a single FRAX token (excluding any gas and fees). At this end of the interval, FRAX is fully algorithmic using the value of the FXS token; think “UST stablecoin and Luna governance token”.

### Redeeming FRAX

The variable $$C_r$$ also determines how FRAX tokens are redeemed. No matter when the token in question was minted, when it is submitted for redemption the protocol returns $$C_r$$ collateral and $$1-C_r$$ dollars worth of minted FXS.

### Price Stability

When $$C_r = 1$$, the price of FRAX is as stable as its collateral.

When $$C_r < 1$$, and the price of FXS is greater than 0, there is an arbitrage opportunity created whenever the price of FRAX moves above or below $1. When FRAX is priced above $1, one can mint FRAX for $1 worth of collateral and FXS, and then sell the newly minted FRAX for the higher price. This arbitrage opportunity exists until Frax is priced at $1 again. When the price of FRAX moves below $1, one can purchase FRAX for the lower price and redeem it for $1 worth of collateral and FXS.&#x20;

**Modeling Question:** we know these stabilizing forces failed to prevent price depegging in the case of UST/LUNA. For a given value of $$C_r$$, how much FRAX price volatility can this mechanism handle?

## Algorithmic Market Operations (AMOs)

### Dynamically adjusted $$C_r$$

The FRAX docs describe a way to compare FXS liquidity to total supply of FRAX tokens called the [PIDController](https://docs.frax.finance/amo/fxs1559). First they describe an approximation of FXS liquidity, and then take the ratio of this approximation and total supply of FRAX tokens.

If the PIDController is increasing, then there is more FXS liquidity available relative to total supply of FRAX. This increased available value from FXS implies that $$C_r$$ can be decreased (ie, FRAX value can lean more on FXS value rather than collateral) without impacting the solvency of the protocol. When $$C_r$$ is decreased, it contributes negatively to the rate of change of the PIDController. Another way to say this is that when $$C_r$$ is decreased, it slows down the PIDController increase, possibly stopping its movement altogether or reversing its direction.

If the PIDController is decreasing, there is less available FXS liquidity relative to total supply of FRAX, and increasing $$C_r$$​ may be required to maintain protocol solvency. When $$C_r$$​ is increased, it contributes positively to the rate of change of the PID controller, slowing down its decrease and possibly stopping its movement altogether or reversing its direction.

In both cases, the impact of $$C_r$$​ on $$\textrm{PIDController}$$ depends on volume of FRAX minting/redemption.

**Modeling Question:** What is the impact of $$\Delta C_r$$​ on $$\Delta \textrm{PIDController}$$? How does this depend on: volume, $$C_r$$, $$\textrm{PIDController}$$?

**Modeling Question**: Compare the approximation of FXS liquidity to the actual liquidity of the FXS token. What can we say about the difference, and how does it impact the PIDController strategy?

### The basic AMO

The FRAX protocol's parameter $$C_r$$​ is automatically adjusted in response to PIDController movement.

1. When PIDController is increasing, $$C_r$$​ is decreased.
2. If the PIDController is not moving (enough),  $$C_r$$​ remains unchanged.
3. When PIDController is decreasing, $$C_r$$​ is increased.
4. As the FRAX protocol accrues collateral in excess of $$\textrm{Total Supply of Frax} * C_r$$, these additional funds are used to mint an equivalent amount of FRAX, which are then used to purchase FXS on AMMs, which are then burned. This mechanism is designed to move (per capita) value of FRAX above $1 to the FXS token.

### More general AMOs

FRAX protocol allows for the creation of independent smart contracts that act in a similar way to the basic AMO. They are required to have the [following specifications](https://docs.frax.finance/amo/overview):

1. Decollateralize - some smart market actions that users can activate that impacts the $$C_r$$ by lowering it. The FRAX [documentation](https://docs.frax.finance/amo/overview) still mentions this is only permitted when the price of FRAX is above $1, but we wonder whether newer permissions consider PIDController instead.
2. Equilibrium - market actions that do not impact $$C_r$$.
3. Recollateralize - some market actions that users can activate that impacts $$C_r$$​ by raising it. There is mention of permissions depending on price of FRAX falling below $1, but we wonder whether this is permissioned by the PIDController.
4. FXS Value Accrual Mechanism - a formal accounting of the additional value of the AMO, and a strategy for using that excess value to acquire and burn an equivalent amount of FXS (thereby transferring the excess value to the FXS token)

The following examples of AMOs are described in the FRAX documentation.&#x20;

#### [Collateral Investor](https://docs.frax.finance/amo/collateral-investor) AMO

#### [Curve](https://docs.frax.finance/amo/curve) AMO

#### [Uniswap v3](https://docs.frax.finance/amo/uniswap-v3) AMO

#### [Collateral Hedge](https://docs.frax.finance/amo/collateral-hedge) AMO

#### [FRAX Lending](https://docs.frax.finance/amo/frax-lending) AMO

#### Token:

{% embed url="https://etherscan.io/token/0x853d955acef822db058eb8505911ed77f175b99e" %}

**Contract:**

{% embed url="https://etherscan.io/address/0x853d955acef822db058eb8505911ed77f175b99e#code" %}

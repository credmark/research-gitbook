# Bancor

The Bancor protocol operates as a decentralized exchange, allowing users to provide liquidity in its pools and to use those liquidity pools to perform permissionless swaps. Its protocol token is Bancor Network Token (BNT), an ERC-20 token with some additional functionality. Some unique features of the Bancor DEX are:

* the ability to provide single-sided liquidity
* the guarantee of impermanent loss (IL) protection
* BNT acting as the central medium of exchange for all tokens.

The precise implementation details change from v2.1 to v3, and we discuss them below.

### Bancor v2.1

#### Pools

In Bancor v2.1, every (non-BNT) tradable token (TKN) has a single pool in which it trades against BNT. For example, there is a BNT-wETH pool, a BNT-LINK pool, and a BNT-DAI pool. Users may provide liquidity on either side of a pool: BNT or TKN.

#### Providing Liquidity

In many AMMs, a liquidity provider is required to provide liquidity on both sides of the trade, and in proportion that is determined by the relative asset price. Suppose I want to provide liquidity in a BNT-wETH pool in a constant product AMM. If the price of wETH in the pool is 1000 BNT, then when providing liquidity to the pool I must provide 1000 times more BNT than ETH, so that the liquidity provided in ETH is of equal value to the liquidity provided in BNT. Typically I would receive some number of Liquidity Provider (LP) tokens for that pool that represent my share of the pool’s liquidity.

In v2.1, liquidity providers may provide liquidity on just one side of the pool, meaning that in a BNT-wETH pool, I can provide 1 ETH without providing an equal amount of (or any) BNT. This flexibility for users requires a little added complexity from v2.1.

1. To track contributions, v2.1 pools each have two LP tokens
   * An LP token tracking how much BNT a user has staked in the BNT-TKN pool, let's call it tknBNT.
   * An LP token tracking how much TKN a user has staked in the BNT-TKN pool, let's call it bnTKN.
2. Some behavior to keep BNT and TKN liquidity matched when users provide liquidity on one side.
   * When a user provides liquidity to the pool in TKN, the Bancor protocol mints new BNT to match the value of newly added TKN liquidity and provides the BNT-liquidity side to the BNT-TKN pool. The user depositing TKN is given bnTKN to track their deposit, and the protocol takes the tknBNT from its corresponding BNT deposit. When one-sided wETH liquidity leaves the pool, Bancor returns the tknBNT and burns the corresponding BNT.&#x20;
   * When a user provides one-sided BNT liquidity to a pool, they are given tknBNT and Bancor burns an equal amount of its own BNT liquidity position in the pool. When one-sided BNT liquidity leaves a pool, Bancor mints an equal amount of BNT and provides it to the pool.

#### Impermanent Loss Insurance

Impermanent loss insurance in v2.1 ramps up to 100% coverage **over the course of 100 days after deposit**. Because Bancor protocol is acquiring LP tokens when users provide liquidity on one side of a trade, the protocol is also earning a good amount of trading fees, both in BNT and in TKN. The protocol burns BNT fees and saves TKN fees in reserve to pay out users who experience IL and are covered by the protocol insurance. When TKN fees are insufficient to pay out users experiencing IL, BNT is minted to cover the IL.

**Modeling question:** How can we measure the health and reliability of v2.1 insurance reserves?

**Modeling question:** What do the insurance reserves for v2.1 pools look like historically?

**Modeling question:** How do reserves change by pool, and how is that correlated with TKN's volatility? How often do users experience impermanent loss?&#x20;

**Modeling question:** How much IL can the protocol actually cover?

#### Pool Pricing

Many AMM pools use an internal price function for swaps that only uses information readily available to the pool’s smart contract (some examples: relative liquidity in the pool, recent swap volume in the pool, some constants related to the pool’s tokens). When the internal price of a pool’s smart contract moves out of sync with the ambient market price, many AMMs rely on arbitrage between their pools and external markets to bring their pool price back in sync with the ambient market price. This strategy relies on arbitrageurs extracting value from the users of the AMM pool in order to keep the AMM price accurate:&#x20;

* From traders: in the form of paying too much when making large purchases
* From liquidity providers: in the form of impermanent loss&#x20;

Bancor v2.1 guarantees its users that the protocol itself will pay for impermanent loss, and so the protocol aims to protect its pools from this kind of arbitrage.

In order to protect v2.1 pools from arbitrage, the protocol tracks market prices through the use of on-chain oracles. Pools in v2.1 use Chainlink oracle price updates every 10 minutes, and use a moving-average to compute the price in between these updates. When users want to swap in a  v2.1 pool, they do so with this Chainlink price.

#### Dynamic weighting

Even with price oracles offering some protection from IL, swaps in a pool can move TKN reserves out of balance with the amount of existing bnTKN, which creates the possibility of liability for Bancor protocol. That is, if 1000 LINK have been deposited in total in the BNT-LINK pool, there will be a total supply of 1000 bnLINK tokens. If trades in the BNT-LINK pool have moved the actual link reserves down to 800 LINK, then Bancor is on the hook for returning 200 LINK that it currently does not hold.

To incentivize the markets to equalize actual TKN reserves with existing supply of bnTKN, markets have dynamically updating weights which create BNT incentives for users to swap TKN back into the pool.

**Modeling question:** Do these BNT incentives actually cost less than the price of arbitrage that v2.1 pools are trying to avoid?

#### Pool Size

Pools in v2.1 are capped at certain liquidity limits.

#### Double fees

All trades TKN1-->TKN2 on v2.1 must actually pass through two trades: TKN1--> BNT followed by BNT-->TKN2.

### Bancor v3

For simplicity, we'll just track some important changes from v2.1 to v3.

#### Omnipool

In v3 all tokens are held by a single "vault contract." Swaps are still executed with BNT as the central medium of exchange in the virtual sense that prices are all computed in the background using BNT, but trades TKN1 --> TKN2 no longer have to actually enact two swaps on chain.

Another consequence of omnipool is that there is no longer a different LP token for BNT for each available TKN. Instead, all staked BNT is staked into the / against the rest of the omnipool. So when v3 mints BNT to stake against a single-sided LINK deposit, or when v3 mints BNT to stake against a single-sided DAI deposit, it mints bnBNT for both transactions, as well as bnLINK for the first and bnDAI for the second.

#### IL insurance

Instead of 100 day ramp up to full IL protection, v3 provides 100% IL protection immediately but requires a 7 day cool-down period for withdrawing liquidity.

#### AMM structure

Rather than using a dynamically weighted, oracle-priced AMM, v3 switches to a classical constant-product AMM structure.

**Modeling Question**: Why switch to a constant product AMM?&#x20;

**Modeling Question:** What does constant product IL in v3 do to the price and value of BNT token over time?&#x20;

#### Infinity Pools

Bancor v3 allows for pools to have uncapped liquidity.

### Bancor in the news

#### Halting IL protection

On June 19, 2022 Bancor [announced](https://blog.bancor.network/market-conditions-update-june-19-2022-e5b857b39336) that "Due to hostile market conditions, Bancor’s Impermanent Loss Protection is temporarily paused." They [suggest](https://twitter.com/fullyallocated/status/1538958972476342272), as Twitter user @fullyallocated notes, that "that 3AC and Celsius have been farming massive amounts of volume in Bancor, and they have recently withdrawn their deposits and sold their BNT into the pool for remaining assets."

**Modeling question:** Consider the [hypothesis](https://twitter.com/fullyallocated/status/1538958976523837440) presented by @fullyallocated: "this happened before Bancor paused their ILP, meaning the protocol paid out these entities in full, plus incurred a huge IL debt on their remaining deposits from the BNT \[that 3AC and Celsius] dumped. As a result, Bancor is experiencing liquidity issues on their outstanding deposits." Is this hypothesis supported by the data?&#x20;

Some [preliminary data](https://twitter.com/fullyallocated/status/1538959005485510656) on Bancor's liquidity seems to indicate that they may owe 15,000 ETH, 3.5 million LINK, and 1.3 million DAI in IL protection.

#### Nansen Alpha report on v3

In April 2022, Nansen Alpha released a Twitter thread [describing the findings](https://twitter.com/nansen\_alpha/status/1509805674598854656) in their report on Bancor v3. Their findings include a [summary of changes](https://twitter.com/nansen\_alpha/status/1509805685898244097) in v3, but do not mention the transition from dynamic AMM to constant product AMM.&#x20;

**Modeling Question:** what is the cost of IL to Bancor protocol in v2.1 compared to v3? How does the change in market structure between v2.1 and v3 impact the cost of IL for the Bancor protocol?&#x20;

The Nansen Alpha report seems to [praise](https://twitter.com/nansen\_alpha/status/1509805688691707906) Bancor v3 for addressing a primary pain point by uncapping pool sizes.&#x20;

**Modeling Question:** What benefit does v3 gain from uncapped pools? What kind of risk does this expose them to on the IL insurance side?

The report also [touches on the danger](https://twitter.com/nansen\_alpha/status/1509805699844374528) of holding BNT when IL protection is paid for by inflating supply of BNT, but seems to [conclude](https://twitter.com/nansen\_alpha/status/1509805702532923397) that "this is not necessarily true and may reflect a lack of understanding of Bancor’s unique tokenomics which are sometimes inflationary, sometimes deflationary, with the net being close to zero."

**Modeling Question:** Under what market conditions are Bancor's tokenomics deflationary?&#x20;

**Modeling Question:** What is the current net impact of IL on BNT's value? Has it netted out to close-to-zero?

The report [mentions](https://twitter.com/nansen\_alpha/status/1509805711114469376) another risky looking metric for BNT: "As the graph shows, approximately 90% of BNT is on exchanges. This is typically a warning sign - given that a high balance on exchanges means that the token can be easily sold." Again, the report seems to conclude that this warning sign is [not as risky as it seems](https://twitter.com/nansen\_alpha/status/1509805714193084420).

**Modeling Question:** What if anything has the high availability of BNT tokens cost the protocol during these "hostile market conditions"?

The report [describes](https://twitter.com/nansen\_alpha/status/1509805725215645698) Bancor v3 as "a genuinely useful product in single-sided staking and IL protection."

**Modeling Question:** How could we model the potential costs of IL protection to Bancor / BNT?

**Modeling Question:** What kinds of benefits (wider adoption, higher trading volume) would be required to make Bancor v3 profitable (when considering the costs of IL protection)?

### Bancor v3 contracts

The current Bancor v3 smart contracts can be found [here](https://docs.bancor.network/developer-guides/contracts).

## Contributors

| Discord Handle  | ETH Address | Reward            | Contribution     |
| --------------- | ----------- | ----------------- | ---------------- |
| corepresentable |             | 0 $CMK (internal) | Original version |

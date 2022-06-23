# Overview of Investment Platforms

## Executive Summary <a href="#docs-internal-guid-fbcff4a5-7fff-5347-72f0-4b68f2ab781a" id="docs-internal-guid-fbcff4a5-7fff-5347-72f0-4b68f2ab781a"></a>

This document lists down some of the existing protocols that are being used by Liquidity Providers to collectively invest and manage their positions in the field of DeFi, be it lending and borrowing assets on Aave and Compound or providing liquidity in protocols like Uniswap V2 and V3 to earn transaction fees. \


## Platforms

### dHedge

[https://app.dhedge.org/](https://app.dhedge.org/)

​dHEDGE is a one-stop location for managing investment activities on-chain where you can put your capital to work in different strategies based on a transparent track record

Managers create pools through the dHEDGE factory. Each pool is its own contract.

Managers may have public pools allowing anyone to become an investor. Managers may also have private pools which allow only whitelisted investors to invest.

Managers can use active management strategies, algorithmic strategies, or invest in other pools on dHEDGE. Automated strategies are possible with the [dHEDGE SDK](https://docs.dhedge.org/developers/developers).

When an investor deposits into a dHEDGE pool, they are issued pool tokens, which represent their share of the assets under management (AUM) for a given pool.

Ethereum v1 pools require Synthetix's native stablecoin, sUSD, to invest.&#x20;

On Polygon pools, investors may invest with any asset the manager of that pool has enabled for depositing.

Investors can track exactly what trades a manager has made, and see what assets are currently in the manager's pool.

![](https://lh4.googleusercontent.com/H8LLkthbivaEsdJPBj9wOAm-Fiq5ZKL3\_GKf7oP6aer\_BiVjyu9y-3QGBHVqKDSiiv\_cyad86apI9sgvVDKAtraXWsdQFib4ax3qbLVbmq9o38R7XNoGgwAyE1XdKsjPaPppyzcT)

![](https://lh5.googleusercontent.com/ZvpcK-pRqtFzBSHzwS6c\_fMQ7ro4lV3M1E80G49B3\_IkizTFMuWf\_Ya9VPdBUveHd7HSZZGDVff0r28YX-YtVYlx\_V3r6SqMEPEpdmHr09ZFAL1doYKAR7z\_okIvn14l13Q3R7JE)

![](https://lh6.googleusercontent.com/PcFJjUNNkx3SjGTxbdm87zpYTq8Joxs1t6SzT2ZK08p6bPKOMxO9dEXZhsPLo6lIfHC4obvt3pUIjILLRJQPCFUw-030Klt\_hAUDZ50VQjl759PoHcNM4hMsSOn\_D0E85K9XF46D)

Investors may enter or exit a pool at any time by interacting with the pool smart contract. By default, all pools have a 24-hour lockup after investing. This provides flashloan protection and arbitrage protection.

dHedge currently supports Ethereum network along with layer 2 solutions like Polygon and Optimism.

While only Spot Trading is available on ethereum network, dHedge on Polygon supports Spot Trading, Lending & Borrowing, Liquidity Provision and Leverage.

For example- Managers can provide liquidity in Sushi, then stake that liquidity for extra yield.

Managers are sorted on the basis of

1. Most value Managed
2. Top Ranked
3. Top Performing

Investors can view and compare the pools managed by value managed, returns, rewards and risk factor.

![](https://lh3.googleusercontent.com/em6EKVYO509j2ql0EyPZgOdVMueUTX6eFHNK6GMKJ11vRk7VRj8zZfJoQVjPmB3rlOdw2LFYVSBo\_yKzcZVIZQ0tVLXQHVpQlNDkP0mHnseWaKUjYizpb0VUHWsYOdWC8rahIQRe)

#### Breakdown

Almost all top strategies in dHedge have a green 1 year return with some reaching as high as 800%

![](https://lh6.googleusercontent.com/ibfBgGWog-kn2qeDSrssovfSoaRvCqFs3rONX6bGTSu8x\_C-Ekb35zWuh6UNKVThHu4MH73koqy-Cvj-oYMszw3NK9AdsmhLGJJpRge05YRGU6HIg4NtJZrcN7yZ9I\_hC\_sqbS-J)

\


dHedge is not limited to just providing liquidity and instead can be collectively used with other protocols such as lending protocols, AMMs giving high returns.

We will be breaking down the strategy with the Highest Value Managed on dHedge.

[dHEDGE Stablecoin Yield](https://app.dhedge.org/pool/0xbae28251b2a4e621aa7e20538c06dee010bc06de)

This strategy is managed by dHedge itself and is the strategy with highest value managed close to $2.4 million with 139 unique investors.

This strategy currently gives an APY of 7.54% along with 7.7% APY in DHT (dHedge’s native token) and taxes a performance fee of 5%.

![](https://lh5.googleusercontent.com/yfn9cZQQKhZ2bMxnJZTSlYCfPilPM5HIC949bq\_2kby-AFv1BpOnwFFGSfq1A2UjD70oHitnVBHRTj4VNrteC4g3ZSWdPbIOoogb8cGvpp2Y3gcuyhqSeImiMFxdiohJmLowc\_eF)

dHEDGE Stablecoin Yield pool (dUSD) will algorithmically farm the highest supported stable pool on Polygon.

It will switch farming pools when higher stable yield opportunities arise over time, ensuring optimal performance.

The pool can have exposure to FRAX, USDC, DAI, USDT. These get added as liquidity and staked in order to earn yield. Every time the pool stakes more tokens, it will automatically harvest the rewards and rebalance the newly acquired stablecoins to equal weighing. After ensuring equal weighing, the pool then provides those assets as liquidity and stakes. Investors have the flexibility of depositing one of the farmed stablecoins.

Investments are also covered by InsurAce for certain types of hacks.

### Charm Finance (Alpha Vaults)

[https://charm.fi/](https://charm.fi/)

Alpha Vaults is an automated LP vault for Uniswap V3. It was the first Uniswap V3 LP vault to launch; and the simplest, most stable, and highest returning LP vault of its kind.

Key Features

1. Higher yields using the new concentrated liquidity feature in V3.
2. Automatically rebalances  so that your inventory remains balanced. LPs don’t have to worry about managing their position — they can just leave their deposit in the vault.
3. Executes rebalance passively using range orders to avoid swap fees and price impact.
4. Automatically collect trading fees from the Uniswap pool.
5. Vault shares are represented as ERC-20 tokens so are composable and fungible.
6. Saves LPs a ton of gas. A tiny amount of gas fees only have to be paid when entering/exiting the vault.

Two major downsides with Alpha Vaults is that investors can only invest in vaults managed by Charm Finance.They are yet to launch their Alpha Pro version in which any manager can create a vault and strategy for any pair and 5% of the fees from Uniswap go to the Charm treasury, used to cover the vault's running costs. &#x20;

Alpha Vaults also do not support any network other than ethereum and is therefore prone to high gas fees rebalances.&#x20;

Track record of every vault in Alpha Vaults can be viewed by following this [link](https://dune.xyz/mxwtnb/Alpha-Vaults-Performance?Number%20of%20days=200).

![](https://lh3.googleusercontent.com/F2Bn3ziboh6dTYRpYqojD-YKQpZxu0ALqnGj66CA4K55QoyVpn1ddXs9FY4mRPsmhCZ91ZMHjy9WbQkVMjc0X1HVrIbdEL8tmUbFrkPnzRhXIKll61lJzJOUXNe7RKa84nq0CU\_V)

#### Breakdown

There are five vaults deployed on Alpha Vaults for providing liquidity on Uniswap V3 with only three active vaults for the most active liquidity pools,i.e., ETH/USDT, ETH/USDC and WBTC/USDC.

WBTC/USDC vault has a TVL of $3.5 million with only 42.6% of capital used.

WETH/USDC vault has a TVL of $4 million with only 27.2% of capital used while WETH/USDC vault has a TVL of $1.6 million with only 27.2% of capital used\


![](https://lh3.googleusercontent.com/0kiEQmCZoDOOyCaBTi0B1NjlVooLByU9L0qur1aXU2g1HQ-0z7VB7kzVf8yuZkn-3eyKNNVY\_69mYbzUno8Q9VNCKomvz8TGflFqc3Hz5DUj-FhqM62-sWBOOxYtgL258ynP-mv4)

Lets’ break down the vault with Highest TVL on Alpha Vaults.

[WBTC / USDC Alpha Vault](https://alpha.charm.fi/vault/0xBD7c6D2edE836b6b27C461799c4e9ecB8F4e8A66)

This is the strategy with the highest TVL on Alpha Vaults approximately $2.8 million with 2:1 WBTC to USDC ratio.

Alpha Vaults doesn’t show the APY for any vault on its dashboard but this vault claims to automatically manage liquidity on Uniswap V3 for you.

It concentrates its liquidity to earn higher yields and automatically adjusts its range orders as the underlying price moves so that it can continue to capture fees.

Performance fees is set at 5% and go to Charm’ Treasury.&#x20;

By using a passive rebalancing strategy to rebalance its inventory, it avoids paying swap fees on Uniswap or suffering from price impact.

This vault has currently two active positions in Uniswap V3 with base order between 29345 - 60648 and limit order on 42313 - 47708

### Lixir Finance

[https://lixir.finance/](https://lixir.finance/)

Lixir Finance, like Alpha Vaults, is an automated LP vault for Uniswap V3. When a user deposits assets into one of these vaults, the protocol adds the assets to its liquidity position in an external AMM (e.g. Uniswap V3) in order to start gaining yield for the user.&#x20;

Managers are not privileged to create their own vaults for managing liquidity. In order to compound the accrued LP fees that are collected separately in Uniswap V3 and make sure a proper LP range is maintained such that capital efficiency is optimized, a keeper is set in place and responsible for calling the rebalance function.&#x20;

Currently this happens every 6 hours, but Lixir proposes that in the near future the timing of rebalances will be dictated by a data-backed, algorithmic strategy.

The performance fees collected by the protocol is not listed and vary for vaults.

Lixir only supports five top assets and is also devoid of using layer two networks such as Polygon to reduce high gas fees rebalances.

#### Breakdown

Currently, 6 pools and strategies are deployed on Lixir finance with APY reaching as high as 292% with TVL of $80k in its toop pool of WBTC/WETH.

![](https://lh6.googleusercontent.com/0hfCyVg3KyDi373sKOpG-PyhTNdAeN5TRewIV1y8h0qc0uzRIdwIyOOI6BT9D-n-SBQxItV2nm4VecAsor1XVwM9XZ0fTQJoiH5beCl7JzO6-VGuJp07gpbf6EhcH9ofGmGFZP2Q)

### Visor Finance

[https://www.visor.finance/](https://www.visor.finance/)

Visor describes itself as tooling for active liquidity management on concentrated liquidity AMM's such as Uniswap v3. Visor developed a series of smart contracts and management infrastructure used by managers and market makers. Visor has merged with Gamma Strategies

The published data and analytics dashboards can be found on [Dune Dashboards](https://dune.xyz/gammastrategies) an

![
](https://lh5.googleusercontent.com/OOshlXwSaslkqNe7\_l0YJx5J10BU4fID0Ky65sGGU6qpyOdBNyp55PL9egUu9BTruK2M235fv5w--HO2iG\_aFlqH59peXMEoybp\_5TLBf5LoDNcXjpMWHWVdbRhgId\_avxOo-pBG)

Unlike Alpha vaults and Lixir Finance, Visor allows managers to create their own vaults and strategies.

Also, Visor supports each and every pair on Uniswap V3 along with layer 2 network; Polygon.

Visor Finance has more than $10+ million in active liquidity with $6.87 million in fees collected.

![](https://lh3.googleusercontent.com/yAdadTAgfE2tb8GeNi6ec3k5w18A7kN17bbH6zCD2fgwyNxsud4WspeYzIr\_h-p8zSLpAE1hNp7AbgqD2pQEcQBKBbcO4p-Rauh2YEdKxT3knWy7DBOHhe0VopkBYMMGSrbbTM2o)

#### Breakdown

Visor finance have provided with an average fee-based APR of 25% for its GAMMA token.

&#x20;

![](https://lh3.googleusercontent.com/bGu22tfRZcGKqC8u42oQkTSg5Y9VT8IvOu6ympN\_zFhN2BTezXEI8jbbqh56gCx8x8o87Emz\_aesHjXA9ji-WzUFlULjuLbSZa5VuWf2qv-YVQsfdvqAzenYyRwEmhwHQvvmEwf7)

### Aloe Capital(Blend Vaults)

[https://aloe.capital/](https://aloe.capital/)

The Aloe Protocol is a liquidity allocator for AMMs, targeting Uniswap V3 at launch. Aloe Blend uses a hybrid liquidity management system that's designed to earn more trading fees for liquidity providers (LPs) without requiring them to select specific ranges or manually move their funds around.

Aloe Blend Vaults address the problems of managing liquidity and unpredictable value changes. To achieve the same impermanent loss and volatility characteristics as Uniswap V2, Aloe Blend uses the same liquidity density as a 0->infinity position. To achieve higher yields, assets far from the current price are deposited to yield platforms, rather than sitting dormant like they would in Uniswap. This design stands in contrast to other V3 position managers, which exclusively concentrate liquidity.

![](https://lh4.googleusercontent.com/AW3OFsxMvGhV23XAMvT-eePog5ajgIq-2Gxc3DiuSgkK6QATJfw3-3B6ukiPJSGrqmF2mr4Ef-ueoL7VcDGlzcZW9LLWUCKaLKz2V18wRf3DY0Xuihj2oyRcLn\_9Gt5vq2EZGX9v)

Managers are privileged with the option to create their own Blend Vault. Pool creators have no special access or control. Once a pool is deployed, all users are treated equally.

Aloe Capital’s Blend vaults tackle a different approach from other “concentrated liquidity provider protocols” by converting Uniswap V3 to 0 to infinity type liquidity range of Uniswap V2 and deploying unused capital to other protocols such as Compound and Yearn for additional lending and farming rewards.

![](https://lh5.googleusercontent.com/8lZ-QhENrJE1TZHQvjcooLJuEpAZl-JJoNUEE0JF\_vSGwvEjSnhMyiE5DIdfcZYrimaUjZ1oyIppr-AQ5Sg70MKz3\_hgzLNcL4sKWJ96nbMDLV3mGDfK5ZcNk76FEJPyz85m69Af)

#### Breakdown

There are five strategies deployed on Aloe capital for five different pools with average APY of 10% just for deploying the liquidity in Uniswap V3 as we did in V2 and investing the other amount of token elsewhere.

![](https://lh5.googleusercontent.com/dpG2VtfmKrZmRdVieciR-PsBBF5XyJKgjRjROxP2qwpL5tbpxZFXZ8OGdl6hP5Qv6dAXPEXPej5FY4m1507fELBcwTu2oC1CqYF-IyilDfyBiTJlxMZzDgWo0QZm-pjAI\_0IHH4v)

### Universe Finance

[https://www.universe.finance/](https://www.universe.finance/)

Universe Finance is an active liquidity management platform of Uniswap V3 based on risk ranking and quantitative strategies.&#x20;

With a series of products, Universe Finance can meet the needs of LPs who have different risk appetites.

* Uniswap V3 Back-testing Platform
* Uniswap V3 Active LP Quantitative Management Strategy
* Uniswap V3 Smart Vault
* Uniswap V3 Private Vault
* Uniswap V3 Hedging Vault (Developing)

Universe Back-testing is the LP revenue backtesting system on Uniswap V3 with accurate on-chain data, granularity of block-level backtesting, flexible self-defined parameters, and robust strategy analysis indicators. It can help users understand the benefits and the risks of Uniswap V3 LP easier and customize the LP strategies.

It can be accessed from this [link](https://www.universe.finance/backtest?q=0x8ad599c3A0ff1De082011EFDDc58f1908eb6e6D8,480,180,3,2021/06/01,2022/03/24,0,10000,0,270,1).

![](https://lh4.googleusercontent.com/41bON7idhqsFge6txc3VUgv5WOuKwqgvaS-rQh3zZYDWT4vA58gfNLFyPJ8BpOeBxn\_AXzMQvUEMRjwp6ZaT5mqCLue16vviPHBG9niZVVZ\_S5SXxEEwPF3r\_7USP\_JrF8eorhj4)

Universe Finance has $4+ million in active liquidity while over $2+ million in fees collected till now.

![](https://lh3.googleusercontent.com/KzrQ\_lFpvYBUv5qeptBVv3M36IVe0-wT9lASJPa3EPLgHyV2cy458q6AyoizGHsF2lYjJzOujsKTkp9P4Y\_-iXvZm4RfIkJZSJopbuIig3nUASwxwSh5XEnLJ3zLKULmf8PSbcyy)

Universe Finance too doesn't allow managers to create a pool and strategy for investors.

#### Breakdown

There are several vaults deployed on Universe finance smart vaults, some even with 4 digit APY.

![](https://lh3.googleusercontent.com/gdkVQl7IuGah0NgNQ9Xmd4VHWyXV9IxnQC721i5Xq6zomqfSmdVGXTD\_i1H8v4WbJIY3tVoq1E5o0nHXzTqwLF0p9MmxMb7g2RUvHuGfT1frF1i9J1QjhlN3H9abbXH8zInV3Te9)

With 4 vaults of hughes active pools on Uniswap V3

![](https://lh3.googleusercontent.com/jcwqa-mBOB7yVafaGXNml81G65wi6kFLdq7xDjpsR-P\_VZ\_vb0oqxTRU8OgVu2xczIiZy-zP5x5IXhQNNtcqwCEPKFmpiJpDebgpugiQSa559UJk4jwUg7\_YDlfREpWwCj6PzSsw)

## Conclusion

While Universe Finance shows very high APR for some of the strategies, most of the pool consists of shady coins like WRLD, SOS and STRONG which doesn’t offer long term value to the liquidity providers and also snapshots for APR are not regularly updated.

Lixir Finance and Visor Finance are too complicated to use because of their UI, which seems like an unfinished project and redundant because of their lack of transparency.

Alpha Vaults only supports Accumulated Liquidity Providing on Uniswap V3 with only 5 strategies and also doesn’t display the metrics like APR on its dashboard to distinguish between the different choices.

dHedge emerges as the winner out of all these protocols with services such as providing liquidity to AMMs and with lending protocols simultaneously, easy to use UI, presence of existing different strategies with completely different approaches and risk appetite of investors, transparent activities’ record and various metrics for each strategy like risk factor, performance APR for different time-frames and much more.

### Contributors

| Discord Handle   | ETH Address                                    | Reward           | Contribution     |
| ---------------- | ---------------------------------------------- | ---------------- | ---------------- |
| **airboom#0400** | **0x84eAF08c13E86cD1603Bb8de7f5F61Fa115771bc** | 0 CMK (internal) | Original version |

\

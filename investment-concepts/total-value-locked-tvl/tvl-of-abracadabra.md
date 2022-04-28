# TVL of Abracadabra

## Executive Summary

Total value locked (TVL), in the context of cryptocurrency, represents the sum of all assets deposited in decentralized finance (Defi) protocol earning rewards, interest, new coins, tokens, fixed income, etc.

The TVL numbers shown on third-party sources and dashboard don’t match. And that raises the question of which one is accurate and how these numbers are calculated.

We dig deeper into how it’s being calculated by Abracadabra and we found that third-party sources are not accurate and have a deviation of 14% from the actual value.

## Abracadabra

is a lending platform that uses interest-bearing tokens (ibTKNs) as collateral to borrow a USD pegged stable coin (Magic Internet Money - MIM), that can be used as any other traditional stable coin.

Abracadabra provides an analytics dashboard \[7] that sums up the whole platform quite nicely. But the question arises, how is Abracadabra calculating all those details. For our discussion, we would be focusing on TVL. How is it calculated? How can we use that information?

There are third parties like Defillama \[11], Dune \[12], and DefiPulse \[13] that provide this information for a lot of platforms out there. It does help us to get a bigger picture of the TVL and other metrics between a lot of platforms and insights out of them. But, when it comes to the source of information and the particulars of RAW data used in the calculation, there are not many details available. In this document, we will be getting into how Abracadabra calculates its TVL.

For TVL calculation, since the value required is in terms of USD, Abracadabra uses centralized exchange coingecko to get the current price of some of those tokens. For the tokens that are not available on coingecko, oracles are used to get the price. We will be discussing these tokens in more detail while calculating the TVL

TVL of Abracadabra is spread across 5 chains, namely:&#x20;

1. Ethereum&#x20;
2. Fantom&#x20;
3. Arbitrum&#x20;
4. AVAX&#x20;
5. Binance

## Abracadabra TVL Calculation

To calculate the TVL of Abracadabra we need to find the TVL across each chain and add them up. To calculate TVL across each chain, we use the contracts \[6] to get the balance tokens in each of them. The balance indicates the number of tokens of the assets. That balance is multiplied by the asset’s USD value to get asset-wise TVL. We then sum up all the assets TVL to get Chain’s TVL.

But how abracadabra is getting the current prices of the assets? It’s using \[8] coingecko API to get the current USD price of selected assets. There are some assets (wrapped) that are not available on coingecko. For those tokens, yearn oracle is being used \[9] to get the current USD price.

List of tokens not available on coingecko:&#x20;

1. yvCurve-IronBank&#x20;
2. yvCurve-stETH&#x20;
3. yvWETH&#x20;
4. Stkcvxcrv3crypto-abra&#x20;
5. stkcvxcrvRenWBTC-abra

The following calculations were done on **8 Feb 2022 at 7:30 PM GMT.**

Dashboard = **$ 3.89 Bln**&#x20;

Defillama    = **$ 3.35 Bln**

![](<../../.gitbook/assets/image (8).png>)

### Ethereum Chain - TVL:

| **Asset**                  | **Number of Tokens** | **USD Price** |   **USD Value** |
| -------------------------- | -------------------: | ------------: | --------------: |
| ALCX                       |                35798 |        184.13 |         6591495 |
| FTM                        |            169094174 |          2.33 |       393989426 |
| wsOHM                      |                   23 |        6581.7 |          156356 |
| xSUSHI                     |              2392507 |          6.11 |        14618222 |
| yvCurve-IronBank \[5]      |             30418655 |          1.15 |        34981454 |
| yvCurve-stETH \[1]         |                72398 |    2808.21999 |       203310291 |
| yvWETH \[2]                |                73663 |       3191.09 |       235067989 |
| Stkcvxcrv3crypto-abra \[4] |               182705 |       1557.09 |       284488800 |
| SHIB                       |          32249550744 |     3.338e-05 |         1076490 |
| stkcvxcrvRenWBTC-abra \[3] |                  708 |      44839.52 |        31758171 |
| AGLD                       |                70878 |          1.26 |           89306 |
| FTX Token                  |              4492102 |         47.92 |       215261533 |
| SPELL                      |           1981124626 |    0.00693462 |        13738346 |
| sSPELL                     |           9895571470 |    0.00693462 |        68622027 |
| UST                        |            101219597 |           1.0 |       101219597 |
| stkcvx3Crv-abra            |             69126309 |         27.39 |      1893369626 |
| WETH                       |                14606 |       3153.41 |        46059935 |
| WBTC                       |                 1349 |         44073 |        59432297 |
| **Total TVL**              |                 **** |               | **$ 3.60 bln**  |

### Fantom Chain - TVL:

| Asset                 | Number of Tokens | USD Price                | USD Value       |
| --------------------- | ---------------- | ------------------------ | --------------- |
| Wrapped Fantom (WFTM) | 13783486         | 2.32                     | 31977688        |
| WFTM yVault (yvWFTM)  | 51709305         |  2.32                    | 119965589       |
|                       |                  | **Total TVL ( Fantom )** | **$ 0.153 bln** |

### Arbitrum Chain - TVL:

| Asset                      | Number of Tokens | USD Price      | USD Value      |
| -------------------------- | ---------------- | -------------- | -------------- |
| Spell Token (SPELL)        | 1182253370       | 0.00693462     | 8306937        |
| Magic Internet Money (MIM) | 143973642        | 1              | 143753614      |
|                            |                  | **Total TVL**  | **$ 0.15 bln** |

&#x20;           &#x20;

Avalanche and Binance chains have TVL less than 100 mln so not considering for current calculations \[10].

&#x20;     &#x20;

| Chain          | TVL ( bln )  |
| -------------- | ------------ |
| Ethereum       | $ 3.60       |
| Fantom         | $ 0.153      |
| Arbitrum       | $ 0.15       |
| **Total TVL**  | **$ 3.903**  |

### Observations

1. The number approximately match with the dashboard with a deviation of 0.2% and is higher from what defillama states by 14%.
2. There is a periodic update in the abracadabra analytics dashboard which might cause the difference in given and calculated TVL.
3. Abracadabra relies on both centralized (coingecko) and decentralized sources (oracles) to calculate the TVL of the platform.

### Why is Defillama's TVL different?

Abracadabra maintains tokens in two vaults:

* Bentobox Vault \[15]
* Degenbox Vault \[16]

To calculate the TVL, we need to sum all the tokens across both these vaults to get the TVL.&#x20;

Now Defillama uses Abracadabra's API \[17] to fetch the TVL which only tracks the assets present in Bentobox. That difference in tracked assets creates the deviation of 14% as observed above. Whereas, the dashboard tracks of all the vaults while calculating the TVL.

## References:

1. Curve Finance, https://curve.fi/steth&#x20;
2. Zerion, https://app.zerion.io/invest/asset/yvWETH-0xed0244b688cf059f32f45e38a6ac6e479d6755f6&#x20;
3. Zerion, https://app.zerion.io/invest/asset/renCrv-0x49849c98ae39fff122806c06791fa73784fb3675&#x20;
4. Zerion, https://app.zerion.io/invest/asset/3CrvCrypto2-0xc4ad29ba4b3c580e6d59105fff484999997675ff&#x20;
5. Zerion, https://app.zerion.io/invest/asset/yvCurve-IB-0x27b7b1ad7288079a66d12350c828d3c00a6f07d7&#x20;
6. Abracadabra, https://docs.abracadabra.money/our-ecosystem/our-contracts&#x20;
7. Power BI, https://app.powerbi.com/view?r=eyJrIjoiOGFjN2QyMDgtMzRhMy00NDkzLTk2NDctNTBkZTQ0NzQ3ZjJkIiwidCI6IjYyZTU1MTgwLTQzNmQtNDYyZC1hMWIwLTZkMTg2NjRlZDAxNSJ9&#x20;
8. Github, https://github.com/Abracadabra-money/user-interface/blob/main/src/utils/helpers.js&#x20;
9. Github, https://github.com/Abracadabra-money/user-interface/blob/cb608e43f0c79e9a975419cd4ea9eea60907d82a/src/utils/contracts/oracle.js&#x20;
10. Defillama, https://defillama.com/protocol/abracadabra&#x20;
11. Defillama, https://defillama.com/&#x20;
12. Dune, https://dune.xyz/browse/dashboards&#x20;
13. Defipulse, https://www.defipulse.com/&#x20;
14. Coindesk, https://www.coindesk.com/learn/why-tvl-matters-in-defi-total-value-locked-explained/
15. Sushuswap, https://docs.sushi.com/products/bentobox
16. Medium, https://medium.datadriveninvestor.com/money-the-degenbox-guide-37d54fc4c4da
17. Github, https://github.com/DefiLlama/DefiLlama-Adapters/blob/main/projects/abracadabra/api.js

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 $CMK (internal) | Original version |

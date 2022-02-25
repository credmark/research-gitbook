# Aave Data Discrepancy

### Executive Summary

This document explains the discrepancy between **assets’ balance data** obtained using various approaches used to extract the data of lending protocol,[ **Aave**](https://aave.com).

**The three approaches used are -**&#x20;

1. Aave Native API
2. Smart contract(On-chain) Data Extraction
3. Subgraph API

We will use these three approaches to fetch assets balance on Aave and compare the results in findings.

### List of Assets supported on Aave:

#### February, 2022

| address                                    | token\_name             | token\_symbol |
| ------------------------------------------ | ----------------------- | ------------- |
| 0x9f8F72aA9304c8B593d555F12eF6589cC3A579A2 | Maker                   | MKR           |
| 0xdAC17F958D2ee523a2206206994597C13D831ec7 | Tether USD              | USDT          |
| 0x2260FAC5E5542a773Aa44fBCfeDf7C193bc2C599 | Wrapped BTC             | WBTC          |
| 0xC02aaA39b223FE8D0A0e5C4F27eAD9083C756Cc2 | Wrapped Ether           | WETH          |
| 0x0bc529c00C6401aEF6D220BE8C6Ea1667F6Ad93e | yearn.finance           | YFI           |
| 0xE41d2489571d322189246DaFA5ebDe1F4699F498 | 0x Protocol Token       | ZRX           |
| 0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984 | Uniswap                 | UNI           |
| 0x7Fc66500c84A76Ad7e9c93437bFc5Ac33E2DDaE9 | Aave Token              | AAVE          |
| 0x0D8775F648430679A709E98d2b0Cb6250d2887EF | Basic Attention Token   | BAT           |
| 0x4Fabb145d64652a948d72533023f6E7A623C7C53 | Binance USD             | BUSD          |
| 0x6B175474E89094C44Da98b954EedeAC495271d0F | Dai Stablecoin          | DAI           |
| 0xF629cBd94d3791C9250152BD8dfBDF380E2a3B9c | Enjin Coin              | ENJ           |
| 0xdd974D5C2e2928deA5F71b9825b8b646686BD200 | Kyber Network Crystal   | KNC           |
| 0x514910771AF9Ca656af840dff83E8264EcF986CA | ChainLink Token         | LINK          |
| 0x0F5D2fB29fb7d3CFeE444a200298f468908cC942 | Decentraland MANA       | MANA          |
| 0x408e41876cCCDC0F92210600ef50372656052a38 | Republic Token          | REN           |
| 0xC011a73ee8576Fb46F5E1c5751cA3B9Fe0af2a6F | Synthetix Network Token | SNX           |
| 0x57Ab1ec28D129707052df4dF418D58a2D46d5f51 | Synth sUSD              | sUSD          |
| 0x0000000000085d4780B73119b644AE5ecd22b376 | TrueUSD                 | TUSD          |
| 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48 | USD Coin                | USDC          |
| 0xD533a949740bb3306d119CC777fa900bA034cd52 | Curve DAO Token         | CRV           |
| 0x056Fd409E1d7A124BD7017459dFEa2F387b6d5Cd | Gemini dollar           | GUSD          |
| 0xba100000625a3754423978a60c9317c58a424e3D | Balancer                | BAL           |
| 0x8798249c2E607446EfB7Ad49eC89dD1865Ff4272 | SushiBar                | xSUSHI        |
| 0xD5147bc8e386d91Cc5DBE72099DAC6C9b99276F5 | renFIL                  | renFIL        |
| 0x03ab458634910AaD20eF5f1C8ee96F1D6ac54919 | Rai Reflex Index        | RAI           |
| 0xD46bA6D942050d489DBd938a2C909A5d5039A161 | Ampleforth              | AMPL          |
| 0x8E870D67F660D95d5be530380D0eC0bd388289E1 | Pax Dollar              | USDP          |
| 0x1494CA1F11D487c2bBe4543E90080AeBa4BA3C2b | DefiPulse Index         | DPI           |
| 0x853d955aCEf822Db058eb8505911ED77F175b99e | Frax                    | FRAX          |
| 0x956F47F50A910163D8BF957Cf5846D573E7f87CA | Fei USD                 | FEI           |

### Approach 1: Aave Native API

Aave has also released its native [API](https://aave-api-v2.aave.com) to provide information about the protocol. API operations are mostly read only, used for extracting data and information from and not to interact with the protocol.

We have used “/data/liquidity/v2” to extract information about the Aave Lending pool on a specific date.

The two arguments required to use this method are-

1. poolId - constant for Aave(0xb53c1a33016b2dc2ff3653530bff1848a515c8c5)
2. date - This is an optional argument to prefill the date of data required. We will use the current date in this field to get the latest data.

![Aave V2 API](https://lh3.googleusercontent.com/Zw5Kd9NN516Y35BRRrlduchXORFm2JpMVLpwStSmkimBFV\_cVTh7XXH7B1pPWXEprTsC9Gyx\_GjEwskNzc8jHZ5QfdL-kTuURlpi\_72kYgqJ-4bpuapM59SQlpJCL1uOqQXhjIGB)

Example:

```
https://aave-api-v2.aave.com/data/liquidity/v2?poolId=0xb53c1a33016b2dc2ff3653530bff1848a515c8c5&date=02-14-2022
```

A JSON response is returned - containing all asset’s address as keys and all the required information about an asset such as symbol, totalLiquidity, availableLiquidity, utilizationRate, reserveLiquidationThreshold, aToken Id, totalDebt and much more.

#### Screenshots:

![](https://lh4.googleusercontent.com/vp0wMxxtykh3aVyUSCjobRXhHnbbu1cRxk5GQi2np7cX1bbuy\_bD0bQJOyrrBOdGDHXfsM\_\_qmn3YOIGSenSkDWycOiIA5i-qutxSSaBrakyzh-py\_K-h0IbP9UlrcgeKGse8wzx)

![](https://lh5.googleusercontent.com/ocBd4kFDZJvQJuEwCPc3Br-THKz\_ZxRvY5Zi9F8dwlpl44kYOwBBcbhbfgMwu6Hw8ShdJp8t99C8GFBgLE-D4ZRsBkIOHcKRfThehDvCHaHxDjGeG76BggoiNLmU3h83KGlBvJH8)

![](https://lh3.googleusercontent.com/07cwCgvGT2SHnbLSoZJyuzrfDH8lF29L6yVIxSlg1p8Trb5gSCPStkyS1CL8ruxEKApWylISGX2CBFMGo9GXjgi3RcFlBxKhNWWbukLwIj0N8VwifhinMpb2PJGl-aPp1MBClOY6)

![](https://lh5.googleusercontent.com/T0QWrowU70J2cfli8ShJM1Xw5shCHbUwAkc-x5wW0Mj4CeVVBIJ1EagaBLludcAflj8leYurWB7\_Pqvr4-iIL5ssMtQf-dPU6z9XT8UeopmqOOxQ-gMqI2tXpEdDgWu3c8a4kta-)

![](https://lh5.googleusercontent.com/sz7LgXkQgvfG5TvXMh4hawpUV6kZMbo3GO\_\_ExDj-PdSYDG6cDpXpJkXCTUqkLn4c2ZdFv9bL7IjewkLekCTRmP9EQZTyayx85CBp7CKVbU7-DWqfS4VL-Z-k7j1inG-0cTDi1RC)

From the Aave Native API, we created a list of all the assets along with their total liquidity.

#### List of all the assets listed on Aave along with their total liquidity(fetched from Aave Native API)

Last updated: February 15, 2022



| **Name**                | **Symbol** | **Liquidity** |
| ----------------------- | ---------- | ------------- |
| TrueUSD                 | TUSD       | 99286578.18   |
| Rai Reflex Index        | RAI        | 8157110.553   |
| Gemini dollar           | GUSD       | 13396621.31   |
| yearn.finance           | YFI        | 1547.69506    |
| Basic Attention Token   | BAT        | 6777266.018   |
| Decentraland MANA       | MANA       | 24637961.49   |
| DefiPulse Index         | DPI        | 129230.4452   |
| Uniswap                 | UNI        | 2878551.51    |
| Wrapped BTC             | WBTC       | 24319.74252   |
| Republic Token          | REN        | 56045175.52   |
| Binance USD             | BUSD       | 15294988.93   |
| ChainLink Token         | LINK       | 18671273.2    |
| Synth sUSD              | SUSD       | 35701630.08   |
| Dai Stablecoin          | DAI        | 1498946078    |
| Aave Token              | AAVE       | 1527410.319   |
| Frax                    | FRAX       | 45385513.41   |
| SushiBar                | XSUSHI     | 9316893.281   |
| Paxos Standard          | PAX        | 14375556.06   |
| Fei USD                 | FEI        | 52596577.59   |
| Maker                   | MKR        | 50644.1003    |
| USD Coin                | USDC       | 3565996279    |
| Balancer                | BAL        | 603664.3261   |
| Synthetix Network Token | SNX        | 729388.0264   |
| Wrapped Ether           | WETH       | 1389734.095   |
| Ampleforth              | AMPL       | 11786055.07   |
| renFIL                  | RENFIL     | 64653.72322   |
| Curve DAO Token         | CRV        | 15175545.96   |
| Tether USD              | USDT       | 1049140301    |
| Kyber Network Crystal   | KNC        | 833018.9422   |
| 0x Protocol Token       | ZRX        | 25297360.92   |
| Enjin Coin              | ENJ        | 10005187.06   |

### Smart contract(On-chain) Data Extraction

Total value of an asset deposited in Aave cannot be calculated just by using asset balance in a smart contract. As the reserves deposited in Aave lending pools by depositors are also loaned out to borrowers, using on-chain methods to calculate the balance of assets in the lending pool may not give a true picture of the quantity of actual assets deposited.&#x20;

Aave issues aTokens when a deposit is made in Aave Lending Pool. To measure the actual amount of an asset in Aave Lending Pool, we start by measuring the total supply of the underlying aTokens issued by Aave to depositors upon depositing into the reserves aTokens are only issued when capital is deposited in the lending pool.

First we will find out the smart contract address of all the aTokens issued by Aave using Aave API.

![atoken addresses via Aave API, Python sample code](https://lh4.googleusercontent.com/oYbxUtX8qJoaaIhJD7x48nb5tbOgZEuvCwJFCzBgx-rzLwYHqaGSkV0ulsU4FIEF9cD75\_00RhzrlFpxO5mGn\_t\_GSn2rgsOvc1Sbc0v3ld\_VmP02A0TyEnRJJI2OlgU-8vkuwON)

#### List of the totalSupply of all the aTokens issued by Aave -

Last updated: 15 Feb 2022

| **Name**                     | **Symbol** | **TotalSupply** |
| ---------------------------- | ---------- | --------------- |
| Aave interest bearing TUSD   | aTUSD      | 99274149.94     |
| Aave interest bearing RAI    | aRAI       | 8146899.208     |
| Aave interest bearing GUSD   | aGUSD      | 13392360.18     |
| Aave interest bearing YFI    | aYFI       | 1547.473585     |
| Aave interest bearing BAT    | aBAT       | 6775573.137     |
| Aave interest bearing MANA   | aMANA      | 24669167.88     |
| Aave interest bearing DPI    | aDPI       | 129230.4462     |
| Aave interest bearing UNI    | aUNI       | 2896530.606     |
| Aave interest bearing WBTC   | aWBTC      | 24604.88525     |
| Aave interest bearing REN    | aREN       | 56044068.29     |
| Aave interest bearing BUSD   | aBUSD      | 14983283.28     |
| Aave interest bearing LINK   | aLINK      | 18729743.3      |
| Aave interest bearing SUSD   | aSUSD      | 42381254.85     |
| Aave interest bearing DAI    | aDAI       | 1493385392      |
| Aave interest bearing AAVE   | aAAVE      | 1527607.64      |
| Aave interest bearing FRAX   | aFRAX      | 45386901.69     |
| Aave interest bearing XSUSHI | aXSUSHI    | 9285934.626     |
| Aave interest bearing USDP   | aUSDP      | 14375480.24     |
| Aave interest bearing FEI    | aFEI       | 52600379.68     |
| Aave interest bearing MKR    | aMKR       | 50926.20456     |
| Aave interest bearing USDC   | aUSDC      | 3449091445      |
| Aave interest bearing BAL    | aBAL       | 602006.5357     |
| Aave interest bearing SNX    | aSNX       | 730952.9551     |
| Aave interest bearing WETH   | aWETH      | 1386523.377     |
| Aave interest bearing AMPL   | aAMPL      | 2638599.918     |
| Aave interest bearing RENFIL | aRENFIL    | 64653.37823     |
| Aave interest bearing CRV    | aCRV       | 15190146.52     |
| Aave interest bearing USDT   | aUSDT      | 1045632913      |
| Aave interest bearing KNC    | aKNC       | 833021.9773     |
| Aave interest bearing ZRX    | aZRX       | 25298319.56     |
| Aave interest bearing ENJ    | aENJ       | 10112863.98     |

### Subgraph API

The Graph is the hosted service that provides data and information using subgraphs from the ethereum network by querying the network using GQL language.

Aave’s subgraph is hosted on [this](https://thegraph.com/hosted-service/subgraph/aave/protocol-v2).

To use the subgraph for TVL calculation of Aave, an API needs t be defined which will run the GQL query on the network and return the information requested.

In case of Aave, API for using subgraph is - [https://api.thegraph.com/subgraphs/name/aave/protocol-v2](https://api.thegraph.com/subgraphs/name/aave/protocol-v2)

Further a query needs to be defined to access the information required and will be passed as parameter in the API request.

```
query = """
{
  reserves (where: {
    usageAsCollateralEnabled: true
  }) {
    id
    name
    symbol
    decimals
    price {
      id
    }
    liquidityRate
    variableBorrowRate
    stableBorrowRate
    availableLiquidity
    totalLiquidity
  }
}
"""

```

#### List of all the assets listed on Aave along with their total liquidity(fetched from subgraph API)

Last updated: 15 Feb 2022



| **Name**                    | **Symbol**      | **Liquidity**   |
| --------------------------- | --------------- | --------------- |
| TrueUSD                     | TUSD            | 97287228.16     |
| Uniswap V2                  | AmmUniWBTCUSDC  | 4.70E-11        |
| yearn.finance               | YFI             | 1529.517087     |
| Basic Attention Token       | BAT             | 6753910.08      |
| Decentraland MANA           | MANA            | 24540761.22     |
| DefiPulse Index             | DPI             | 129229.4578     |
| Balancer Pool Token         | AmmBptWBTCWETH  | 0.08732430541   |
| Uniswap                     | UNI             | 2892323.856     |
| Wrapped BTC                 | AmmWBTC         | 15.96082112     |
| Wrapped BTC                 | WBTC            | 24589.7542      |
| Uniswap V2                  | AmmUniYFIWETH   | 3.49029135      |
| Uniswap V2                  | AmmUniCRVWETH   | 0.4136273303    |
| Republic Token              | REN             | 55999644.19     |
| Uniswap V2                  | AmmUniSNXWETH   | 0               |
| Gelato Uniswap DAI/USDC LP  | AmmGUniDAIUSDC  | 0.0999997548    |
| ChainLink Token             | LINK            | 18725482.49     |
| Balancer Pool Token         | AmmBptBALWETH   | 139.5231672     |
| Dai Stablecoin              | AmmDAI          | 1081260.234     |
| Dai Stablecoin              | DAI             | 1442950180      |
| Aave Token                  | AAVE            | 1527568.242     |
| SushiBar                    | XSUSHI          | 9279134.206     |
| Uniswap V2                  | AmmUniRENWETH   | 0               |
| Fei USD                     | FEI             | 50290199.51     |
| Maker                       | MKR             | 50907.39918     |
| USD Coin                    | AmmUSDC         | 793914.1441     |
| USD Coin                    | USDC            | 3307066754      |
| Uniswap V2                  | AmmUniLINKWETH  | 256.3532883     |
| Uniswap V2                  | AmmUniDAIWETH   | 6.546891512     |
| Uniswap V2                  | AmmUniDAIUSDC   | 9.09E-06        |
| Uniswap V2                  | AmmUniUSDCWETH  | 0.000424577307  |
| Uniswap V2                  | AmmUniBATWETH   | 17.35398495     |
| Balancer                    | BAL             | 595281.7211     |
| Uniswap V2                  | AmmUniWBTCWETH  | 0.0001540129553 |
| Synthetix Network Token     | SNX             | 673443.7833     |
| Wrapped Ether               | AmmWETH         | 2231.906179     |
| Wrapped Ether               | WETH            | 1384418.831     |
| Uniswap V2                  | AmmUniMKRWETH   | 83.43121757     |
| Gelato Uniswap USDC/USDT LP | AmmGUniUSDCUSDT | 4.00E-18        |
| Uniswap V2                  | AmmUniUNIWETH   | 773.7108537     |
| Curve DAO Token             | CRV             | 13860338.3      |
| Kyber Network Crystal       | KNC             | 785907.7743     |
| Uniswap V2                  | AmmUniAAVEWETH  | 3.043532669     |
| 0x Protocol Token           | ZRX             | 25293998.32     |
| Enjin Coin                  | ENJ             | 10090381.63     |

### Findings

#### Difference between assets’ balance fetched from Aave Native API and total supply of corresponding aTokens



| **aName**                    | **aSymbol** | **aTotalSuply** | **underlyingSymbol** | **Name**                | **Symbol** | **Liquidity\_API** | **Difference**   | **Difference Percentage** |
| ---------------------------- | ----------- | --------------- | -------------------- | ----------------------- | ---------- | ------------------ | ---------------- | ------------------------- |
| Aave interest bearing TUSD   | aTUSD       | 99274149.94     | TUSD                 | TrueUSD                 | TUSD       | 99286578.18        | 12428.23636      | 0.01251753921             |
| Aave interest bearing RAI    | aRAI        | 8146899.208     | RAI                  | Rai Reflex Index        | RAI        | 8157110.553        | 10211.3443       | 0.1251833506              |
| Aave interest bearing GUSD   | aGUSD       | 13392360.18     | GUSD                 | Gemini dollar           | GUSD       | 13396621.31        | 4261.13          | 0.03180749759             |
| Aave interest bearing YFI    | aYFI        | 1547.473585     | YFI                  | yearn.finance           | YFI        | 1547.69506         | 0.2214746321     | 0.01430996569             |
| Aave interest bearing BAT    | aBAT        | 6775573.137     | BAT                  | Basic Attention Token   | BAT        | 6777266.018        | 1692.881161      | 0.0249788212              |
| Aave interest bearing MANA   | aMANA       | 24669167.88     | MANA                 | Decentraland MANA       | MANA       | 24637961.49        | -31206.38634     | -0.126659774              |
| Aave interest bearing DPI    | aDPI        | 129230.4462     | DPI                  | DefiPulse Index         | DPI        | 129230.4452        | -0.0009759872773 | -7.55E-07                 |
| Aave interest bearing UNI    | aUNI        | 2896530.606     | UNI                  | Uniswap                 | UNI        | 2878551.51         | -17979.09585     | -0.6245882968             |
| Aave interest bearing WBTC   | aWBTC       | 24604.88525     | WBTC                 | Wrapped BTC             | WBTC       | 24319.74252        | -285.1427294     | -1.172474294              |
| Aave interest bearing REN    | aREN        | 56044068.29     | REN                  | Republic Token          | REN        | 56045175.52        | 1107.229558      | 0.00197560191             |
| Aave interest bearing BUSD   | aBUSD       | 14983283.28     | BUSD                 | Binance USD             | BUSD       | 15294988.93        | 311705.6553      | 2.037959339               |
| Aave interest bearing LINK   | aLINK       | 18729743.3      | LINK                 | ChainLink Token         | LINK       | 18671273.2         | -58470.10692     | -0.3131554356             |
| Aave interest bearing SUSD   | aSUSD       | 42381254.85     | SUSD                 | Synth sUSD              | SUSD       | 35701630.08        | -6679624.768     | -18.70957923              |
| Aave interest bearing DAI    | aDAI        | 1493385392      | DAI                  | Dai Stablecoin          | DAI        | 1498946078         | 5560685.863      | 0.3709730421              |
| Aave interest bearing AAVE   | aAAVE       | 1527607.64      | AAVE                 | Aave Token              | AAVE       | 1527410.319        | -197.321072      | -0.01291866825            |
| Aave interest bearing FRAX   | aFRAX       | 45386901.69     | FRAX                 | Frax                    | FRAX       | 45385513.41        | -1388.28037      | -0.003058862324           |
| Aave interest bearing XSUSHI | aXSUSHI     | 9285934.626     | XSUSHI               | SushiBar                | XSUSHI     | 9316893.281        | 30958.65449      | 0.332285168               |
| Aave interest bearing FEI    | aFEI        | 52600379.68     | FEI                  | Fei USD                 | FEI        | 52596577.59        | -3802.089041     | -0.007228776502           |
| Aave interest bearing MKR    | aMKR        | 50926.20456     | MKR                  | Maker                   | MKR        | 50644.1003         | -282.1042547     | -0.5570328094             |
| Aave interest bearing USDC   | aUSDC       | 3449091445      | USDC                 | USD Coin                | USDC       | 3565996279         | 116904833.7      | 3.278321807               |
| Aave interest bearing BAL    | aBAL        | 602006.5357     | BAL                  | Balancer                | BAL        | 603664.3261        | 1657.790329      | 0.2746212188              |
| Aave interest bearing SNX    | aSNX        | 730952.9551     | SNX                  | Synthetix Network Token | SNX        | 729388.0264        | -1564.928677     | -0.2145536559             |
| Aave interest bearing WETH   | aWETH       | 1386523.377     | WETH                 | Wrapped Ether           | WETH       | 1389734.095        | 3210.717949      | 0.2310310987              |

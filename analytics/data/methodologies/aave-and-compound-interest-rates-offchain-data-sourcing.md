# Aave and Compound Interest Rates Offchain Data Sourcing

## Executive Summary <a href="#docs-internal-guid-78efc81e-7fff-8386-4647-3bb974bb4c57" id="docs-internal-guid-78efc81e-7fff-8386-4647-3bb974bb4c57"></a>

This document aims to find and compare the deposit and borrowing rates of the two biggest lending protocols in DeFi along with other important factors such as number of supported assets, utilization rate, total value locked(TVL) and difference between borrowing and lending rate for the same asset in a protocol.&#x20;

These two protocols are [Aave](https://aave.com) and [Compound](https://compound.finance).

Live data for comparison between the protocols has been fetched from native APIs for Aave and Compound.

## Protocol Analysis

### AAVE

#### Introduction

Aave is a decentralized finance protocol that allows people to lend and borrow crypto.

Lenders earn interest by depositing digital assets into specially created liquidity pools. Borrowers can then use their crypto as collateral to take out a secured loan using this liquidity.

#### Task

The task is to extract lending and borrowing data from Aave using Aave’s Native API and present the findings in an exploratory manner.

#### Data Retrieval

Data is retrieved using native API of Aave protocol with python programming language and Jupyter Notebook. Full code is available at this [link](https://drive.google.com/drive/folders/19\_In204dOZSaOGU7FRgwPXu5PmhiECn9?usp=sharing).

Code

```
# Fetching Data from AAVE v2 Data API 
AAVE_DATA = {}


res = requests.get('https://aave-api-v2.aave.com/data/liquidity/v2?poolId=0xb53c1a33016b2dc2ff3653530bff1848a515c8c5').json()
AAVE_DATA = res
    
ASSETS = list()


for i in range(len(AAVE_DATA)):
    
    data = AAVE_DATA[i]


    _name = data['name']
    _symbol = data['symbol']
    _decimals = data['decimals']
    _totalLiquidity = data['totalLiquidity']
    _depositRate = float(data['liquidityRate']) * 100
    _borrowRate = float(data['variableBorrowRate']) * 100
    _availableLiquidity = data['availableLiquidity']
    _lastUpdateTimestamp = data['lastUpdateTimestamp']
    _utilizationRate = data['utilizationRate']
    _totalDebt = data['totalDebt']




    ASSETS.append({'name': _name, 'symbol': _symbol, 'totalLiquidity': _totalLiquidity, 'depositRate': _depositRate, 'borrowRate': _borrowRate, 'availableLiquidity': _availableLiquidity, 'totalDebt': _totalDebt, 'utilizationRate': _utilizationRate, 'lastUpdateTimestamp': _lastUpdateTimestamp})



ASSETS = pd.DataFrame(ASSETS)


ASSETS.head()


ASSETS.to_csv('./aave_assets.csv', index=False)
```

\


**Output**

| **name**                | **symbol** | **totalLiquidity** | **depositRate** | borrowRate    | availableLiquidity | totalDebt   | utilizationRate | lastUpdateTimestamp |
| ----------------------- | ---------- | ------------------ | --------------- | ------------- | ------------------ | ----------- | --------------- | ------------------- |
| TrueUSD                 | TUSD       | 104734420.1        | 1.519311243     | 2.891942091   | 45025245.56        | 59709174.52 | 0.5701007794    | 1645487775          |
| Rai Reflex Index        | RAI        | 8076032.777        | 1.203550915     | 2.772192285   | 3659271.391        | 4416761.386 | 0.5468974072    | 1645452051          |
| Gemini dollar           | GUSD       | 13390137.99        | 0.950539793     | 2.319042306   | 7252577.73         | 6137560.26  | 0.4583642278    | 1645460402          |
| yearn.finance           | YFI        | 1383.094689        | 0.4071549532    | 2.850718126   | 1133.204979        | 249.88971   | 0.1806743327    | 1645464819          |
| Basic Attention Token   | BAT        | 6473045.044        | 0.06260444961   | 1.041234607   | 6041998.155        | 431046.889  | 0.06659105352   | 1645416762          |
| Decentraland MANA       | MANA       | 23596994.09        | 0.07181806392   | 0.8259406091  | 22349224.24        | 1247769.842 | 0.05287833855   | 1645480911          |
| DefiPulse Index         | DPI        | 129247.543         | 0.0006369375753 | 0.1056321317  | 128272.8583        | 974.6847613 | 0.007541224679  | 1645269848          |
| Uniswap                 | UNI        | 2715503.58         | 0.05698606877   | 1.058058141   | 2531770.662        | 183732.9183 | 0.06766071665   | 1645487514          |
| Wrapped BTC             | WBTC       | 24644.49176        | 0.007354716587  | 0.3276302683  | 23989.53766        | 654.9540962 | 0.02657608453   | 1645487725          |
| Republic Token          | REN        | 57646617.08        | 0.0227418282    | 0.5651184298  | 55558306.33        | 2088310.744 | 0.03622607621   | 1645487374          |
| Binance USD             | BUSD       | 13512500.76        | 2.451689026     | 3.736381799   | 3610428.755        | 9902072.01  | 0.7328082479    | 1645474667          |
| ChainLink Token         | LINK       | 18170424.2         | 0.004933111758  | 0.1857114283  | 17953700.07        | 216724.1317 | 0.01192730171   | 1645487941          |
| Synth sUSD              | SUSD       | 34936721.87        | 1.380879657     | 2.970982874   | 14481794.46        | 20454927.42 | 0.5854850232    | 1645398766          |
| Dai Stablecoin          | DAI        | 1236675551         | 2.2556619       | 3.560992734   | 371350377.7        | 865325173.6 | 0.699718833     | 1645487775          |
| Aave Token              | AAVE       | 1522179.943        | 0               | 0             | 1522179.943        | 0           | 0               | 1645487759          |
| Frax                    | FRAX       | 44539380.81        | 1.409510864     | 3.001864961   | 18192158.46        | 26347222.35 | 0.591548914     | 1645440588          |
| SushiBar                | XSUSHI     | 9343436.013        | 3.37E-05        | 0.02841361872 | 9326371.832        | 17064.18088 | 0.001826328221  | 1645477220          |
| Paxos Standard          | PAX        | 14379308.45        | 1.200258588     | 2.45702592    | 6526182.677        | 7853125.774 | 0.5461407133    | 1645458603          |
| Fei USD                 | FEI        | 62836585.27        | 15.26667743     | 23.71419547   | 10394714.9         | 52441870.37 | 0.8345754332    | 1645472259          |
| Maker                   | MKR        | 51234.34461        | 0.001134216231  | 0.1297180272  | 50807.3778         | 426.9668134 | 0.008333605449  | 1645487775          |
| USD Coin                | USDC       | 2860657919         | 1.506179305     | 2.711152101   | 1139654140         | 1721003778  | 0.6016111773    | 1645487587          |
| Balancer                | BAL        | 608042.9957        | 2.30687197      | 6.886036795   | 347719.9327        | 260323.063  | 0.4281326565    | 1645420742          |
| Synthetix Network Token | SNX        | 731353.303         | 2.237296117     | 9.200369692   | 448488.3395        | 282864.9635 | 0.3867692432    | 1645413031          |
| Wrapped Ether           | WETH       | 1420141.357        | 0.01854816587   | 0.4922288092  | 1363484.861        | 56656.49538 | 0.03989496899   | 1645487711          |
| Ampleforth              | AMPL       | 11733533.44        | 0.1524508165    | 1.329214974   | 11450698.73        | 282834.7161 | 0.02410482038   | 1645471867          |
| renFIL                  | RENFIL     | 64656.8087         | 0.1285088177    | 1.323526486   | 54940.07187        | 9716.73683  | 0.1502817263    | 1645228882          |
| Curve DAO Token         | CRV        | 15590814.99        | 13.43620348     | 37.44497519   | 7865893.947        | 7724921.047 | 0.4954789759    | 1645487005          |
| Tether USD              | USDT       | 1039917954         | 1.972279988     | 3.09675687    | 326405047          | 713512906.8 | 0.6861242315    | 1645487711          |
| Kyber Network Crystal   | KNC        | 833120.7184        | 0.817649141     | 3.604000351   | 593428.673         | 239692.0454 | 0.2877038586    | 1645346119          |
| 0x Protocol Token       | ZRX        | 25371311.03        | 0.03954988232   | 0.2835738288  | 24909448.88        | 461862.1518 | 0.01820411059   | 1645460047          |
| Enjin Coin              | ENJ        | 10128398.03        | 0.177937806     | 3.17884194    | 8090835.75         | 2037562.281 | 0.2011732038    | 1645487514          |

\
\
\


**Glossary**

**name** - Name of the asset

**symbol** - Symbol of the asset

**totalLiquidity** - Quantity of asset deposited in Aave

**availableLiquidity** - Quantity of asset currently present with Aave

**totalDebt** - Quantity of asset currently loaned out to borrowers

**utilizationRate** - Ratio of available assets to total liquidity of the asset

**depositRate** - Annual Percentage Yield(APY) of depositors for providing liquidity of an asset

**borrowRate** - Annual Percentage Yield(APY) of protocol from users borrowing asset

l**astUpdateTimestamp**- Timestamp of the last updated entries

### Observations

* Low risk assets generally have the highest utilization ratio as they provide a secure collateral for borrowing the asset and also have one of the highest deposit and borrow rates.
* Medium risk assets have the lowest utilization ratio and also the lowest deposit and borrow rates.
* High risk assets have a higher utilization ratio as compared to medium risk assets and lower when compared from low risk assets and also the same is true for their deposit and borrow rates.
* Fei USD (FEI) is the low risk asset(stablecoin) with highest deposit and borrow rates of 15.27% APY and 23.71% APY respectively.
* Curve DAO Token is the asset with highest deposit and borrow rates of 13.43% APY and 37.44% APY respectively.

## Compound

### Introduction

The Compound Protocol is an Ethereum smart contract for supplying or borrowing assets. Through the cToken contracts, accounts on the blockchain supply capital (Ether or ERC-20 tokens) to receive cTokens or borrow assets from the protocol (holding other assets as collateral). The Compound cToken contracts track these balances and algorithmically set interest rates for borrowers.

### Task

The task is to extract lending and borrowing data from Compound using Compound’s Native API and present the findings in an exploratory manner.

### Data Retrieval

Data is retrieved using native API of Compound protocol with python programming language and Jupyter Notebook. Full code is available at this [link](https://drive.google.com/drive/folders/19\_In204dOZSaOGU7FRgwPXu5PmhiECn9?usp=sharing).

Code

```
# Fetching Data from COMPOUND v2 Data API 
COMPOUND_DATA = {}


res = requests.get('https://api.compound.finance/api/v2/ctoken').json()
COMPOUND_DATA = res['cToken']


ASSETS = list()


for i in range(len(COMPOUND_DATA)):
    
    data = COMPOUND_DATA[i]


    _name = data['underlying_name']
    _symbol = data['underlying_symbol']
    
    _depositRate = float(data['supply_rate']['value']) * 100
    _borrowRate = float(data['borrow_rate']['value']) * 100
    _compDepositRate = float(data['comp_supply_apy']['value'])
    _compBorrowRate = float(data['comp_borrow_apy']['value'])
    
    _totalSupply = float(data['total_supply']['value'])
    _totalBorrows = float(data['total_borrows']['value'])
    _lastUpdateTimestamp = time.time()
    # _utilizationRate = _totalBorrows/_totalSupply
    _availableLiquidity = _totalSupply - _totalBorrows




    ASSETS.append({'name': _name, 'symbol': _symbol, 'totalSupply': _totalSupply, 'depositRate': _depositRate, 'borrowRate': _borrowRate, 'COMP_depositRate': _compDepositRate, 'COMP_borrowRate': _compBorrowRate, 'totalBorrows': _totalBorrows, 'availableLiquidity': _availableLiquidity, 'utilizationRate': _utilizationRate, 'lastUpdateTimestamp': _lastUpdateTimestamp})


ASSETS = pd.DataFrame(ASSETS)


ASSETS.head()


ASSETS.to_csv('./compound_assets.csv', index=False)
```

**Output**

| **name**                  | **symbol** | **totalSupply** | **depositRate** | borrowRate   | COMP\_depositRate | COMP\_borrowRate | totalBorrows | availableLiquidity | lastUpdateTimestamp |
| ------------------------- | ---------- | --------------- | --------------- | ------------ | ----------------- | ---------------- | ------------ | ------------------ | ------------------- |
| Augur                     | REP        | 60946.45157     | 0               | 3.416261581  | 0                 | 0                | 54.67475735  | 60891.77681        | 1646160750          |
| Sai (Legacy Dai)          | SAI        | 8071180.601     | 0               | 5.899807394  | 0                 | 0                | 432.790797   | 8070747.811        | 1646160750          |
| Pax Dollar                | USDP       | 1248407.442     | 0.05319844296   | 0.6379630898 | 0                 | 0                | 2789.013718  | 1245618.428        | 1646160750          |
| yearn.finance             | YFI        | 1634.151349     | 1.19459191      | 7.913199265  | 0                 | 0                | 6.842445981  | 1627.308903        | 1646160750          |
| Fei USD                   | FEI        | 0               | 0               | 0            | 0                 | 0                | 0            | 0                  | 1646160750          |
| Maker                     | MKR        | 546497.7555     | 0.0001181929998 | 2.309208872  | 0                 | 0                | 0.7551349982 | 546497.0004        | 1646160750          |
| TrueUSD                   | TUSD       | 4327162719      | 1.603675905     | 3.18140384   | 0                 | 0                | 48464181.97  | 4278698537         | 1646160750          |
| Wrapped BTC               | WBTC       | 72684.98502     | 0               | 2.320854713  | 0                 | 0                | 0.56727547   | 72684.41774        | 1646160750          |
| Basic Attention Token     | BAT        | 6976015950      | 0.1405993509    | 3.966383585  | 0.4033864546      | 8.71770784       | 6942336.152  | 6969073614         | 1646160750          |
| 0x                        | ZRX        | 5514229657      | 0.3446379059    | 5.373379587  | 0.6725639201      | 7.947963171      | 9941118.635  | 5504288539         | 1646160750          |
| ChainLink Token           | LINK       | 114449664.3     | 0.5940260986    | 5.954853139  | 1.247242699       | 9.503796398      | 314174.0529  | 114135490.2        | 1646160750          |
| Compound Governance Token | COMP       | 28311617.11     | 0.7510673968    | 6.531614701  | 2.098776323       | 0                | 91015.95951  | 28220601.15        | 1646160750          |
| SushiToken                | SUSHI      | 6159074.995     | 6.506724681     | 17.19749484  | 0                 | 0                | 66127.7751   | 6092947.22         | 1646160750          |
| Aave Token                | AAVE       | 678500.5766     | 1.845840792     | 9.562554972  | 0                 | 0                | 3633.030279  | 674867.5463        | 1646160750          |
| Wrapped BTC               | WBTC       | 1553091.713     | 0.1146750788    | 3.429028088  | 0.2355525181      | 5.693014555      | 1323.857227  | 1551767.855        | 1646160750          |
| USDT                      | USDT       | 34859068314     | 2.311811527     | 3.825045901  | 0.3808230239      | 0.5791371332     | 498377075.4  | 34360691239        | 1646160750          |
| Uniswap                   | UNI        | 502635674.1     | 0.282729417     | 5.31778331   | 0.4185654188      | 5.917409419      | 739413.2152  | 501896260.9        | 1646160750          |
| USD Coin                  | USDC       | 123999581159    | 1.633781021     | 3.211355923  | 0.718305691       | 1.299706605      | 1547354922   | 122452226236       | 1646160750          |
| Ether                     | ETH        | 58231247.96     | 0.05283661766   | 2.607023191  | 0.0932638749      | 3.700264954      | 29969.37829  | 58201278.58        | 1646160750          |
| DAI                       | DAI        | 89110178442     | 2.438762643     | 4.102547264  | 1.02974828        | 1.463714917      | 1375077858   | 87735100584        | 1646160750          |



**Glossary**

**name** - Name of the asset

**symbol** - Symbol of the asset

**totalSupply** - Quantity of asset deposited in Compound

**availableLiquidity** - Quantity of asset currently present with Compound(number of tokens available in the asset pool)

**totalBorrows** - Quantity of asset currently loaned out to borrowers

**depositRate** - Annual Percentage Yield(APY) of depositors for providing liquidity of an asset

**borrowRate** - Annual Percentage Yield(APY) of protocol from users borrowing asset

**COMP\_depositRate** - Annual Percentage Yield(APY) of COMP tokens awarded to depositors for providing liquidity of an asset

**COMP\_borrowRate** - Annual Percentage Yield(APY) of COMP tokens awarded to users borrowing asset

**lastUpdateTimestamp**- Timestamp of the last updated entries



### Observations

* DAI is the low risk asset(stablecoin) with highest deposit and borrow rates of 2.44% APY and 4.10% APY respectively along with awarded Compound tokens deposit and borrow rates of 1.03% APY and 1.46% APY
* SushiToken (SUSHI) is the asset with highest deposit and borrow rates of 6.50% APY and 17.19% APY respectively.

## Comparison between both protocols

Based on data points shown above we deduced below findings upon comparing both lending protocols, Aave and Compound.

* Aave(31) supports 50% more assets for lending and borrowing as compared to Compound(20).
* Difference between deposit rates and borrow rates is greater on Compound.
* TVL of Aave($19 bn) is also greater than the compound($11 bn).

Both the protocols have relatively similar user interfaces. But Aave is comparatively easier to use with its on-click borrow and supply buttons.

Aave attracts a more customer base with other networks like Polygon and Avalanche with fractional gas fees as compared to Compound which only supports Ethereum network.

## Contributors

\
\


| **Discord Handle** | **ETH Address**                                              | **Reward**                          | **Contribution** |
| ------------------ | ------------------------------------------------------------ | ----------------------------------- | ---------------- |
| airboom#0400       | <p>0x84eAF08c13E86cD1603Bb8de7f5F61Fa115771bc</p><p><br></p> | <p>0 $CMK (internal)</p><p><br></p> | Original version |

\
\
\
\
\
\
\
\
\
\

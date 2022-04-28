# Abracadabra

Abracadabra is a lending platform that was announced on 5-5-2021. It uses interest-bearing tokens (ibTKNs) as collateral to borrow a USD pegged stable coin (Magic Internet Money - MIM), that can be used as any other traditional stable coin \[1]. Currently, a lot of assets, such as yVaults have locked in the capital that can't be put to further use.

Users can deposit collateral like yvYFI, yvUSDT, yvUSDC, and xSUSHI to get $MIM in return. Their own $SPELL token powers the platform.

The service generates an average of $2.2m per week in fees, with $4.5bn in TVL. At current levels, the platform will render $120m in yearly revenue. $SPELL market cap is $1bn, giving it a price-to-sales ratio of under ten on 19 November 2021\[2].

Overview:

* Provide interest-bearing crypto assets as collateral to borrow MIM (magic internet money).
* MIM is technically stable coins backed by the collateral provided.
* Essentially you can hold onto your yield earning token and borrow money against it which means users can earn while paying debt.
* Return the MIM to release collateral Isolated Lending Market.

## 1. Is It a Protocol or Token? - Both Protocol and Token

Abracadabra is a protocol and a token (SPELL).

## 2. Category

Lending \[3]

## 3. Does it have TVL?

Yes, $5.88 bln. as of 22 January 2022 \[3].

Abracadabra has the following distribution of TVL:

|           |              |
| --------- | ------------ |
| Ethereum  | $4.78 bln    |
| Avalanche | $278.54 mln  |
| Arbitrum  | $297.57 mln  |
| Fantom    | $346.51 mln  |

## 4. How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?

DefiLlama - see current numbers [here](https://defillama.com/protocol/abracadabra).



## 4. What are its core metrics?

As of 22 Jan 2022.

|                                                             |                  |
| ----------------------------------------------------------- | ---------------- |
| Liabilities                                                 | $ 5.88 bln \[4]  |
| Reserves (Amount of MIM tokens available)                   | $2.9 mln \[5]    |
| Assets                                                      | $2.94 bln. \[4]  |
| Treasury                                                    | $4.5 mln \[5]    |
| TVL                                                         | $5.88 bln. \[4]  |
| Market Cap                                                  | $7.15 mln \[6]   |
| The Ratio of Reserves to TVL (deposits only; unleveraged)   | 0.00017          |
| The Ratio of Treasury to TVL (deposits only; unleveraged)   | 0.00076          |
| The Ratio of native Market Cap to TVL                       | 0.00125          |



## 5. Does the protocol have its own Token?

SPELL The protocol's token, that is used for incentivization.&#x20;

sSPELL Obtained by staking SPELL tokens and used for fee-sharing and governance!&#x20;

MIM: A USD pegged stable coin.

![](https://lh5.googleusercontent.com/veu0XpXpGvtEOev82H0wujvqOMj7w7ZYckelelun-WK7g8iuvi0O29sDbEfX80u6mx\_t6QvjNf6WNFgeOYCuBjqCc4PcpFkajBQZhDmsl3xwxC\_T7EZoW5r\_cEspXwVnq8j37\_LL)

Available on following markets \[23] :&#x20;

* Sushiswap&#x20;
* Binance&#x20;
* Coinbase Exchange&#x20;
* BtcTurk&#x20;
* PRO&#x20;
* Gate.io&#x20;
* FTX&#x20;
* Binance&#x20;
* Spookyswap&#x20;
* Uniswap (v3)&#x20;

Liquidity ( On 25th January 2022) \[23]:

* Circulating Supply :    81,546,007,567
* Total Supply :            196,008,739,620
* Max Supply   :           210,000,000,000

## 6. What chain is it on?

Abracadabra lending markets are only available on \[3]

* Ethereum&#x20;
* Binance smart chain&#x20;
* Fantom&#x20;
* Avalanche&#x20;
* Arbitrum

## 7. Could it be exploited?

**Yes**

Abracadabra also provides a Bridge\[9] directly integrated by AnySwap, which allows users’ MIMs to be exchanged directly with each other on Ethereum, Arbitrum, Avalanche, Fantom, and BS.

Could be exploited via bridge cross chains? Yes \[10]

Broadcasts Value&#x20;

* TWAP: Not Applicable&#x20;
* Instantaneous: Not Applicable&#x20;
* Reentrancy risks? : Not Applicable&#x20;
* Using Price Oracles?
  * Abracadabra uses yearn Chainlink oracle which gets a price from Chainlink and uses the following call to access Yearn vault prices \[20].

![](https://lh3.googleusercontent.com/1ISdJMR9flCoSzaJXXnUp-ao72botmCklHxvExlikUO\_b9kaZvntzwUWEG8fqUAoxoZUhWIo-TCdKMlO5AE\_VEUb7PFFTOLXUEe-dlo6-3XhX5BCzl5EMwCmmehuUOlJFNZIN\_IG)

MIM's pegged price is pulled from the 3pool on Curve. If this pool becomes imbalanced and stays imbalanced, this can lead to MIM losing its peg.\
\


## 8. What assets does it support?

What assets does it support\[11]:

![](<../../.gitbook/assets/Screenshot 2022-01-31 at 11.24.34 PM.png>)

## 9. How does it combine the risks of those assets?

A recent example involving Wonderland finance clearly demonstrates the types of risk that exist with Abracadabra.\
\
The UST degenbox strategy has resulted in a large amount of MIM being backed by UST. Additionally, UST price is tethered to MIM as a result of the very popular UST-MIM pool on Curve. During a recent sell off of MIM in response to the Wonderland controversy (Wonderland and Abracadabra are managed by the same team. When one protocol experienced negative press, users responded by dumping the asset of other protocol), the stablecoin lost its peg which subsequently caused UST to lose its peg which, in turn, threatened the integrity of Abracadabra's largest lending markets.&#x20;

This strategy also leverages the Terra ecosystem to generate yield. This is one of the only instances where cross-chain bridging is a linchpin of a yield strategy.  While protocols like Aave exist on other chains, their services and yield stay silo'd on those chains and the user is responsible for moving funds around.

These risks are inherent when a protocol relies almost entirely on algorithmically backed stablecoins \[24].

## 10. Does it wrap and distribute assets?

Yes, an asset is only wrapped when a user wants to use the bridge to transfer the assets to a different chain. In order to bridge tokens, users are required to send them on one chain and receive a wrapped version of the same token on another chain (or L2 solution).

No, It does not distribute assets.

## 11. **What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?**

With all lending and borrowing protocols, there is a chance of liquidation. Liquidation occurs when the value of collateral drops to a predetermined point. Basically, your collateral isn’t enough to cover your debt. This predetermined point is shown once you open your debt position on Abracadabra.&#x20;

In the event that your position is liquidatable, a third party can choose to pay off your debt in exchange for your collateral plus a liquidation fee. If there happens to be any collateral left, users can withdraw it.&#x20;

Remember that each collateral has an independent market on Abracadabra! This is a powerful feature because users can select which assets they are comfortable taking on more risk with, and which they are not \[12].

## 12. **What are the dependencies of the protocol? How does risk bubble up?**

Contrary to Aave and Compound, abracadabra uses Kashi lending technology which means only the specific trading pair is affected should any issue arise whereas the former two shares risk collectively across the entire platform - meaning the choices of collateral will be limited\[1].

Abracadabra’s final score of the review is 43%, a FAIL. by Defi Safety \[17], compared to 96%, AAVE’s final score. The Final score is a security benchmark DefiSafety uses to evaluate protocols. The intent is the generation of a simple quality score for the smart contract application being reviewed. It will indicate the overall quality of the development process and the documents that the process generated.

## 13. Does it have a governance token?

Yes, the name is sSPELL

## 14. How decentralized?

### T**oken :** $SPELL: \[14]&#x20;

* 18,770 holders \[15].&#x20;
* 25,300,000 tokens per wallet&#x20;
* The distribution of the SPELL tokens is as follows:&#x20;
  * 63% (132.3B SPELL): Global Farming Incentives&#x20;
  * 30% (63.0B SPELL): Team allocation (4 Year Vesting Schedule)&#x20;
  * 7% (14.7B SPELL): Initial DEX Offering.

### Decision Making

* SPELL is staked for sSPELL&#x20;
* sSPELL holders: 10,632\[15].&#x20;
* sSPELL grant holders voting rights to change the platform parameters, such as TVL, Liquidation Fees, future collateral options, etc.&#x20;
* sSPELL grant holders a claim on fees generated by the protocol.

### Profits

* 75% of protocol fees are used to purchase SPELL tokens that go to sSPELL token holders.
* 20% is allocated to the governance treasury that will be used to incentive MIM liquidity pools.&#x20;
* 5% is redirected to a multisign treasury that will be used when market conditions require intervention.



## 15. Additional Information

* VAR - provide preliminary insights on how Value-at-Risk can be applied to the protocol Extract historical prices of the token present in abracadabra. Extract the individual token position using the total supply and amount lent to borrowers. Apply VaR calculation&#x20;
* LCR - provide preliminary insights on how LCR can be applied to the protocol Extract Assets and liabilities of the platform for a given date. Apply LCR Calculation
* Abracadabra uses ibTKN that go up in value on their own regardless of price action.
* MIM has interest so if a collateral, for some reason or another, does not increase in value, liquidations can happen. To reduce this risk, the team has selected ibTKNs that have a track record of increasing in value at a rate that far exceeds the interest rate on MIM debt.
* Abracadabra allows for the use of ibTKN with underlying stable coins as collateral with an MCR of 90%. Although it may be unlikely that these ibTKNs will decrease in USD value it’s not an impossibility as the underlying tokens may lose their price pegs from unforeseeable events.
* The Price action of underlying tokens in some of the ibTKNs can be quite volatile. To reduce this risk, the team has set tokens that have price action to have a Maximum Collateral Ratio (MCR) of 75%
* Although any person can perform a liquidation, it has become standard that these functions are performed by bots. Because of this, there is no need for a UI on the main site for this function.&#x20;
* Are there any other metrics that might be useful?&#x20;
  * Sharpe Ratio Sharpe ratio can be calculated for SPELL prices and compared against the peers - other lending protocols to make investment decisions.&#x20;
  * Beta Similarly could be used for SPELL price calculation to compare against similar platforms.

## 16. How is this exposed to layers in DeFi:

### What layers are upstream (built on top of the protocol)?

There are at least two protocols that are using abracadabra upstream. Firstly, Wonderland, is the first decentralized reserve currency protocol available on the Avalanche Network based on the TIME token. Each TIME token is backed by a basket of assets (e.g., MIM, TIME-AVAX LP Tokens, etc) in the Wonderland treasury, giving it an intrinsic value that it cannot fall below. Secondly, Terra Money \[18], that got into partnership with abracadabra \[19].

### What layers are downstream (protocols/assets built on or put into the platform)? For example, yield farms are built on top of lending protocols.

Yearn finance oracle is being used in the platform to get the prices of assets.

## 17. **Smart Contract information**

* [List](https://etherscan.io/accounts/label/abracadabra-money) the protocol´s smart contract address \[22].

| Address                                    | Name                                    |
| ------------------------------------------ | --------------------------------------- |
| 0x7b7473a76d6ae86ce19f7352a1e89f6c9dc39020 | Abracadabra.Money: ALCX Market          |
| 0x806e16ec797c69afa8590a55723ce4cc1b54050e | Abracadabra.Money: Cvx3pool Market      |
| 0x4eaed76c3a388f4a841e9c765560bbe7b3e4b3a0 | Abracadabra.Money: cvxtricrypto2 Market |
| 0x05500e2ee779329698df35760bedcaac046e7c27 | Abracadabra.Money: FTM Market           |
| 0x5f0dee98360d8200b20812e174d139a1a633edd2 | Abracadabra.Money: Multisig             |
| 0xc319eea1e792577c319723b5e60a15da3857e7da | Abracadabra.Money: sSPELL Market        |
| 0x003d5a75d284824af736df51933be522de9eed0f | Abracadabra.Money: wsOHM Market         |
| 0x98a84eff6e008c5ed0289655ccdca899bcb6b99f | Abracadabra.Money: xSUSHI Market        |
| 0xebfde87310dc22404d918058faa4d56dc4e93f0a | Abracadabra.Money: yvcrvIB Market       |
| 0x0bca8ebcb26502b013493bf8fe53aa2b1ed401c1 | Abracadabra.Money: yvstETH Market       |
| 0xffbf4892822e0d552cff317f65e1ee7b5d3d9ae6 | Abracadabra.Money: yvUSDC v2 Market     |
| 0x551a7cff4de931f32893c928bbc3d25bf1fc5147 | Abracadabra.Money: yvUSDT v2 Market     |
| 0x920d9bd936da4eafb5e25c6bdc9f6cb528953f9f | Abracadabra.Money: yvWETH v2 Market     |
| 0xffbf4892822e0d552cff317f65e1ee7b5d3d9ae6 | Abracadabra.Money: yvYFI Market         |

List the Token´s smart contract address&#x20;

* [0x090185f2135308bad17527004364ebcc2d37e5f6 ](https://etherscan.io/address/0x090185f2135308bad17527004364ebcc2d37e5f6)

Are there any other relevant smart contracts\[21]?

|                                     |                                              |                                                                                                                                |
| ----------------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **EthereumWithdrawer**              | 0xB2c3A9c577068479B1E5119f6B7da98d25Ba48f4   | Withdraw MIM fees from cauldron and swap for SPELL. Also used as a recipient for swapping MIM fees received from other chains  |
| **MultichainWithdrawer (BSC)**      | 0xB3f5c7D0Ac3944a9d9A9623D6B50bCeA85A26753   | Not Applicable                                                                                                                 |
| **MultichainWithdrawer(Phantom)**   | 0x7a3b799E929C9bef403976405D8908fa92080449   | Not Applicable                                                                                                                 |
| MultichainWithdrawer (Arbitrum)     | 0x7a3b799E929C9bef403976405D8908fa92080449   | Not Applicable                                                                                                                 |
| MultichainWithdrawer( Avalanche)    | 0x2b95bf93B5873c8cB9aE3374e3054736A5b79676   | Withdraw MIM fees from cauldron and bridge to EthereumWithdrawer                                                               |

## References

1. Abracadabra, https://docs.abracadabra.money/&#x20;
2. Numbrs, https://www.numbrs.com/abracadabra-the-magic-internet-money-spell&#x20;
3. Defillama, https://defillama.com/protocol/abracadabra&#x20;
4. Abracadabra Analytics, https://app.powerbi.com/view?r=eyJrIjoiOGFjN2QyMDgtMzRhMy00NDkzLTk2NDctNTBkZTQ0NzQ3ZjJkIiwidCI6IjYyZTU1MTgwLTQzNmQtNDYyZC1hMWIwLTZkMTg2NjRlZDAxNSJ9&#x20;
5. Abracadabra, https://abracadabra.money/stand&#x20;
6. CoinGecko, https://coinmarketcap.com/currencies/spell-token/&#x20;
7. Abracadabra, https://docs.abracadabra.money/tokens/tokenomics&#x20;
8. Messari, https://messari.io/asset/spell-token&#x20;
9. FootPrint, https://www.footprint.network/article/what-are-cross-chain-bridges-and-why-do-they-matter-fp-619360ce-efc75100-17f31c25&#x20;
10. Abracadabra, https://docs.abracadabra.money/intro/multichain-functionality&#x20;
11. OneDrive, https://1drv.ms/x/s!AnV-I7glMOD4hANW240jd4UUVI7\_?e=4ezNe3&#x20;
12. Abracadabra, https://docs.abracadabra.money/intro/liquidations&#x20;
13. Medium, https://medium.com/abracadabra-money/abracadabra-spell-and-magic-internet-money-a563637ce92e&#x20;
14. Abracadabra, https://docs.abracadabra.money/tokens/tokenomics&#x20;
15. Dune, https://dune.xyz/hammercrypto/Abracadabra&#x20;
16. Seach Index, http://email.raquelfurtado.com/irem7/abracadabra-degenbox.html&#x20;
17. DefiSafety, https://docs.defisafety.com/master/abracadabra.money-process-quality-review&#x20;
18. Terra, https://www.terra.money/&#x20;
19. The Defiant, https://thedefiant.io/abracadabra-and-terra-partnership/&#x20;
20. Boringcrypto. https://boringcrypto.medium.com/magic-internet-money-review-71da416c8824&#x20;
21. Github, https://github.com/Abracadabra-money/magic-internet-money&#x20;
22. Etherscan, https://etherscan.io/accounts/label/abracadabra-money&#x20;
23. Coingecko, https://www.coingecko.com/en/coins/spell-token#markets
24. Coindesk, [https://www.coindesk.com/business/2022/01/28/defi-users-fret-contagion-risk-amid-possible-stablecoin-depegging/](https://www.coindesk.com/business/2022/01/28/defi-users-fret-contagion-risk-amid-possible-stablecoin-depegging/)

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 $CMK (internal) | Original version |




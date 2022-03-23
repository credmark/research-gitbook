# Curve Finance

The easiest way to understand Curve is to see it as an exchange. Its main goal is to let users and other decentralized protocols exchange stablecoins (DAI to USDC for example) with low fees and low slippage. Unlike centralized exchanges that match a buyer and a seller, the behavior of Curve is different as it uses liquidity pools like Uniswap. To achieve this, Curve needs liquidity (tokens) and rewards those who provide it \[1].

### 1. Is it a Protocol or Token?

#### Both a Protocol as well as a Token.

Curve is a popular automated market maker (AMM) platform that offers a highly efficient way to exchange tokens while maintaining low fees and low slippage by only accommodating liquidity pools made up of similarly behaving assets. While this approach results in lower fees for the liquidity providers who supply tokens to the pools, Curve incentivizes their participation by integrating with external Defi protocols and delivering rewards in the form of CRV tokens and interest \[2].

### 2. Category

#### AMM, DEX

### 3. Does it have TVL?

Yes, $23.27 bln. as of 17 January 2022 \[3].

Curve has the following distribution of TVL as of 17 January 2022 \[3]:

| Arbitrum   | $16.6 bln.   |
| ---------- | ------------ |
| Avalanche  | $1.05 bln.   |
| Fantom     | $6.6 bln.    |
| Harmony    | $29.06 mln.  |
| Polygon    | $335.34 mln. |
| xDAI       | $67.15 mln.  |
| Ethereum   | $20.87 bln.  |

#### How is it calculated in different Places (Their Frontend, Dune, DefiPulse, DefiLlama)?

DefiLlama - it is calculated by counting the tokens locked in AMM pools, pulling the data from the respective subgraphs mentioned here \[24].

### 4. What are its...?

As of 17 Jan 2022

* Liabilities: $23,26 bln \[4]&#x20;
* Reserves: $154 mln \[5]
* &#x20;Assets: $21.67 bln \[6]&#x20;
* Treasury: Not available&#x20;
* Market Cap: $1.26 bln \[7]&#x20;
* Ratio of Reserves to TVL (deposits only; unleveraged): 0.010687023&#x20;
* Ratio of Treasury to TVL (deposits only; unleveraged): Not available&#x20;
* Ratio of native Market Cap to TVL (deposits only; unleveraged): 0.08 \[16]&#x20;
* Are they double-counting leverage?  NO

### **5. Further details on the Token?**

**Markets where it’s available?**&#x20;

The list of markets can be found here \[23]&#x20;

* Liquidity: Circulating Supply - the total amount of tokens in circulation $391 mln \[22]&#x20;
* Total Supply - on-chain supply minus burned tokens $1.6 bln \[22]&#x20;
* Max Supply - theoretical maximum as coded $3.3 bln \[22]

### **6. What chain is it on?**

Curve exists across several chains, with several more planned.  Curve's primary chain will always be Ethereum, but other side chains have advantages in terms of transaction speed and gas costs.

Sidechains \[3]:

1\.    Arbitrum

2\.    Ethereum  &#x20;

3\.    Avalanche

4\.    Fantom

5\.    Harmony

6\.    Polygon

7\.    xDAI

### &#x20;**7. Could it be exploited?**

#### **Yes**

There is a security concern where a well-capitalized actor or a flash loan enabled adversary can execute a large swap on Curve to temporarily distort the prices of the two stablecoins involved as compared to the wider market price for those assets. A malicious user can then exploit this price distortion by taking a position on a Defi protocol that offers Curve LP (Liquidity Pool) tokens as a collateral option which also relies on Curve as their price oracle when conducting transactions. The straightforward solution to this issue is to avoid using Curve as a price oracle and to rely on a reliable price oracle that provides an accurate picture of the global market price of the asset in a Liquidity Pool.

An example of an attack is shown in \[9].

As it is Cross-chain, the Curve token can be bridged across some chains but does not always have full functionality. Staking of $CRV for veCRV must be done on Ethereum. Rewards voting for cross-chain gauges occurs on Ethereum.

### **8. What assets does it support?**&#x20;

Curve currently supports trading for the following stablecoins: DAI, USDT, USDC, GUSD, TUSD, BUSD, UST, EURS, PAX, sUSD, USDN, USDP, RSV, LINK, USD. Additionally, you can trade ETH, LINK, and a handful of tokenized BTC assets like wBTC and renBTC.

### **9.** How does it combine the risks of those assets?

From a LP provider perspective, one has to asses the HODL exposure, generated fees and Impermanent Loss (IL). In general, Impermanent loss is higher if prices move more volatile. As Curve mainly deals with stablecoin pools, the impermanent loss is expected to less than with other tokens . Below is the IL (percentage) curve for relativistic price changes \[25].

![](https://lh3.googleusercontent.com/SqiGDlrRoIOQUL27SERfybng8nFeW8YF24zPwFYRIDkuZsaLH8krBimXU4FkCTfLX8BlHhVxTfGRYCd61umTpYfhV513mXhg0sB\_n0jesF0fYpqeoydBkhrK5qze4Q)

### **10. Does it wrap and distribute assets?**

No, Curve doesn't automatically wrap its assets.&#x20;

If you deposit a stablecoin to one of the pools with lending, Curve will automatically wrap your token to a cToken (for Compound) or a yToken(for iEarn).

### **11. What are the conditions for the wrapped assets to be liquidated? Back to the original portfolio or adjusted for value?**

There are no liquidations in case of Curve but assets can become idle. If one of the stablecoins in the pool looses significantly in value and never returns to the original value, it'll effectively mean that pool liquidity providers hold almost all their liquidity in that currency.\[26]

### **12. What are the dependencies of the protocol? How does risk bubble up?**

Curve does not have any dependencies on any third party apps or APIs.

### **13. Does it have a governance token?**

Yes, the name is Curve (CRV) token&#x20;

CRV is the native utility token of the Curve protocol. It has four main use cases: governance, LP rewards, boosting yields (as veCRV), and token burns.&#x20;

**Governance**&#x20;

Curve is a decentralized exchange and is community-governed. Decisions are made on-chain at gov.curve.fi by CRV holders who vote-lock their tokens to convert them into veCRV.&#x20;

**Rewards**&#x20;

Liquidity pool rewards and incentives are paid in CRV to LPs based on the size of the pool share.&#x20;

**veCRV**&#x20;

veCRV stands for vote-escrowed CRV, a fancy name for CRV tokens that have been locked into the Curve protocol for a defined time. veCRV is used for voting in governance, boosting rewards, earning trading fees, and receiving airdrops \[13].

### **14.** How decentralized is it?

* **The Token**  Unique Token Holders - 61695 \[14].&#x20;
* **Decision Making** \[15]&#x20;
  * Anybody can create proposals but users need to follow the structure of a proposal which can be found by creating a new topic on the governance forum: https://gov.curve.fi/&#x20;
  * Users who create proposals also need to create a corresponding CIP proposal at http://signal.curve.fi/&#x20;
  * Using the signaling tool is completely free (no transaction fees) and you only need 1 veCRV to create a proposal there.&#x20;
  * Assuming you have at least 2,500 veCRV, you can also create an official DAO vote as long as it also comes with its topic presenting it on the governance forum.
*   **Profits** \[8]&#x20;

    Currently, CRV tokens have three main use cases: voting, staking and boosting. Those three things will require you to vote, lock your CRV and acquire veCRV.&#x20;

    * **Staking (trading fees)** CRV can now be staked (locked) to receive trading fees from the Curve protocol. A community-led proposal introduced a 50% admin fee on all trading fees. Those fees are collected and used to buy 3CRV, the LP token for the TriPool, which are then distributed to veCRV holders.&#x20;
    * **Boosting** One of the main incentives for CRV is the ability to boost your rewards on provided liquidity. Vote locking CRV allows you to acquire voting power to participate in the DAO and earn a boost of up to 2.5x on the liquidity you are providing on Curve.&#x20;
    * **Voting** Once CRV holders vote-lock their veCRV, they can start voting on various DAO proposals and pool parameters



### 15. Additional Information

* **VAR** - VaR could be applied to manage risk of LPing from a LP provider perspective
* **LCR** - Not applicable&#x20;
* **Are there any other metrics that might be useful?** - Sharpe Ratio could be useful when applied to the CRV token market behaviour&#x20;
* **Annual percentage yield (APY)** - APY is an important metric that any liquidity provider or investor should follow in Curve. APY provides a real rate of return earned on a liquidity pool into account the effect of compounding interest.The below curve highlights the 12-hour and 24-hour APY which provides an idea of the opportunity for liquidity providers in any given pool \[27].

### 16. How is this protocol exposed to the different layers in Defi:

#### What layers are upstream (built on top of the protocol)? Are other protocols that use it as a source of data/pricing oracle, or put funds into it?

Decentralized exchanges (DEXs) use Curve "under the hood" to facilitate currency conversions between coins that otherwise do not have liquid pairs. For example, there might be a liquidity pool for ETH/USDT and CRV/USDT, but no liquidity pool directly between ETH/CRV. What these DEXs do is to convert ETH to USDT first, and then convert USDT to CRV, all in one action (using Curve). All that the user sees is that their ETH has been converted into CRV. Thus, it is the base-layer foundation that many Defi apps sit on top of.

#### What layers are downstream (protocols/assets built on or put into the platform)? For example, yield farms are built on top of lending protocols

Curve uses ctokens from compound **(Compound’s native tokens)**

### 17. Smart Contract information&#x20;

* **List the protocol´s smart contract address:** Curve Finance protocol address :0xa79828df1850e8a3a3064576f380d90aecdd3359 \[17]&#x20;
* **List the Token´s smart contract address:** CRV token tracker address:0xD533a949740bb3306d119CC777fa900bA034cd52 \[18]&#x20;
* **Are there any other relevant smart contracts?** Yes, pools Curve currently support have their unique addresses listed on etherscan with DAI/USDT being most famous 0xbebc44782c7db0a1a60cb6fe97d0b483032ff1c7 \[19]                                                                  All other pools addresses can be found here \[20]\[21]

**References:**

1. Curve, https://resources.curve.fi/base-features/understanding-curve&#x20;
2. Gemini, https://www.gemini.com/cryptopedia/curve-finance-liquidity-provider-dao&#x20;
3. Defilama, https://defillama.com/protocol/curve&#x20;
4. Curve, https://curve.fi/combinedstats&#x20;
5. Curve, https://curve.fi/eurtusd/risks Into the block&#x20;
6. Intotheblock, https://app.intotheblock.com/insights/defi/protocols/curve&#x20;
7. Defipulse, https://defipulse.com/curve-finance&#x20;
8. Curve, https://resources.curve.fi/base-features/understanding-crv&#x20;
9. Twitter, https://twitter.com/emilianobonassi/status/1327716769969164292&#x20;
10. Curve, https://curve.fi/files/01-ToB.pdf&#x20;
11. Quantstamp, https://quantstamp.com/blog/quantstamp-audits-curve-finance-liquidity-mining&#x20;
12. Curve https://curve.fi/eurtusd/risks&#x20;
13. Shrimpy, https://academy.shrimpy.io/post/what-is-curve-finance&#x20;
14. Dune, https://dune.xyz/mrblock\_buidl/Curve.fi&#x20;
15. Curve, https://resources.curve.fi/guides/voting&#x20;
16. Coingecko, https://www.coingecko.com/en/coins/curve-dao-token&#x20;
17. Etherscan, https://etherscan.io/address/0xa79828df1850e8a3a3064576f380d90aecdd3359&#x20;
18. Etherscan, https://etherscan.io/address/0xD533a949740bb3306d119CC777fa900bA034cd52&#x20;
19. Etherscan, https://etherscan.io/address/0xbebc44782c7db0a1a60cb6fe97d0b483032ff1c7&#x20;
20. Etherscan, https://etherscan.io/&#x20;
21. Curve, https://curve.fi/pools&#x20;
22. Coingecko, https://www.coingecko.com/en/coins/curve-dao-token&#x20;
23. Coinmarketcap, https://coinmarketcap.com/currencies/curve-dao-token/markets/&#x20;
24. Defillama, https://defillama.com/protocol/curve&#x20;
25. Yieldapp, https://yieldapp.medium.com/how-do-we-solve-the-impermanent-loss-problem-48d5d5b81e67&#x20;
26. Curve, https://curve.fi/risks&#x20;
27. Medium, https://medium.com/intotheblock/some-cool-indicators-about-uniswap-that-defi-traders-and-investors-should-know-about-6e5138516273

## Contributors

| Discord Handle | ETH Address                                | Reward            | Contribution     |
| -------------- | ------------------------------------------ | ----------------- | ---------------- |
| rlrahulkanojia | 0x784aBff44f2F3bB7c46B789789f3C6552636F4F5 | 0 $CMK (internal) | Original version |
| Deadsec        | 0x1A2E1d4553d33c080746A056AA3F832823fADB51 | 0 $CMK (internal) | Process update   |

&#x20;


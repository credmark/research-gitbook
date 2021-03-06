# Depegging Risk

Depegging risk deals with the issue that a so-called "stable coin" looses its peg. As most stablecoins try to maintain a 1:1 peg to the US-Dollar, a loose of this peg can have serious implications on the protocol that issued the coin as well as the broader crypto ecosystem.

But what are reasons a stablecoin might loose its peg at all? This merely depends on how the current peg is maintained. As the DeFi space gets very creative in creating new stablecoins and mechanisms to algorithmically maintain a peg, we nevertheless need to distinguish between two main possibilities.

### **Peg is secured by USD-reserves**

The easiest way to maintain a peg is to deposit an equivalent amount of US-Dollar into a bank account and only mint the corresponding amount of digital tokens. So for every US-Dollar in the bank exactly one digital token will exist. Thus, it is assured that you will always be able to redeem your token and request the amount in US-Dollar to be paid out.

### **Peg is secured by other crypto assets**&#x20;

As crypto and especially the DeFi-World strives to become independent from the TradFi world and its outdated banking system, several protocols created ways to mint a stablecoin that maintains its peg to the US-Dollar without the need to hold any fiat money in a banking account but instead hold a treasury of other crypto tokens. Based on the US-Dollar value of this underlying basket of tokens, new stablecoins will be either minted or burned in a way to that one stablecoin token always equals one US-Dollar. As the underlying crypto assets are volatile, most protocols (like Maker DAO with its DAI token) require overcollateralization and the protocol will liquidate pledge collateral to maintain the peg.

### **Peg is secured by smart contracts**

As overcollateralization removes a lot of liquidity from the markets, the "newest" versions of stablecoins tried to get rid of any "outside collateral" to maintain their peg. These stablecoins are often called algorithmic stablecoins, as a smart contract automatically rebalances the available amount of outstanding stablecoins to reflect the 1:1 peg to the US-Dollar. The most famous example so far was UST.

### **So how can a Depeg now happen?**

Looking at the first case of US-Dollar reserves in a bank account, the most obvious reason for a depeg to happen is that these reserves do not exist or do not match the outstanding value of stablecoins issued. To prevent this from happening, most companies that issue these type of token publish some sort of audit that confirms the existence of the stated value of US-Dollars in bank accounts. However, if not all of the US-Dollars are held in cash but in short-term securities or other bonds for example, they may not be immediately convertible into US-Dollar cash, which may cause the stablecoin to lose its peg in the event of a bank run.

In terms of algorithmic stablecoins, any manipulation on the value of the underlying tokens can lead to a depeg. This manipulation can be done in several ways, thus incorporating other DeFi-native risks like hacks, exploits, rug pulls or bugs in the underlying smart contracts that create a imbalance of the value for the outstanding stablecoins compared to the value of the underlying assets as collateral.&#x20;

In May 2022 we saw the drama of UST, an algorithmic stablecoin worth more than $18b in market capitalization to loose its peg and causing some severe turmoil on the markets.

{% embed url="https://credmark.com/blog/what-caused-ust-to-de-peg" %}

{% embed url="https://research.thetie.io/trial-of-the-lunatics-the-story-of-anchor-ust-and-luna" %}

{% embed url="https://entrepreneurshandbook.co/luna-brothers-inc-712ec5abe199" %}

### Other Forms of Depeg

Aside from stablecoins, there might occur other forms of Depegging that present risk for investors. Most recently, the stETH token from Lido lost its peg to ETH due to some heavy market turbulence (caused by the UST meltdown) and the need from investors to withdraw their ETH from the biggest stETH/ ETH trading pool on Curve to secure their other leveraged positions.&#x20;

{% embed url="https://blockworks.co/signs-of-next-crypto-depegging/" %}

## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

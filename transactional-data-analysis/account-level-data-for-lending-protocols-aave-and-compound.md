# Account level data for lending protocols (Aave and Compound)

## **Executive Summary:**

To effectively model and implement critical risk metrics for lending service providers (protocols) in Decentralized Finance (DeFi) ecosystem, we first need to analyze and understand the distribution and flow of underlying assets and transactional behavior of different users (wallet addresses) interacting with these protocols. This case study digs into the transactional data of such protocols and presents key insights from the data analysis.

## **Introduction:**

Currently, there are numerous lending protocols available across different block-chains with a variety of asset options for lending and borrowing purposes. But we chose to focus only on two most popular protocols in this space: AAVE and Compound (COMP). The analysis process presented in this article can be replicated to all assets and all other lending protocols on Ethereum blockchain and other chains going forward.

## **Scope:**

Since the same analysis approach can be easily replicated for all assets, to narrow down the scope in sizable number of insights for this article, we only focused on DAI and USDC and fetched insights for H1FY22 only. Hence this article will provide analysis for DAI or USDC related transactions on Compound and AAVE V2 protocol during H1FY22.

## **Method:**

We fetched the on-chain Ethereum data for available via publicly available google big query dataset, sliced the datasets for AAVE V2 and Compound, modeled these datasets for our analysis purposes and used PowerBI tool to visualize the data and fetch insights out of that. The graphs and data (images) shown in this article are from Credmark's in-house PowerBI reports.

## **Compound Protocol Data Analysis**

### **1. Overall Lending pool usage summary for DAI asset**

Below screenshot shows the overall usage summary around DAI  pool and different user actions i.e. lending (aka mint), borrowing, repaying etc.

![DAI pool Transaction Summary (Compound Protocol)](<../.gitbook/assets/image (4).png>)

Summary of different visuals shown in above screenshot is as follows:

**a)**     **Top 10 Users by $:** this visual show the top ten user wallets who have transacted with highest number of DAIs in terms of $ value amount across different user actions.

**b)**    **Top 10 users by Transaction Count:** this visual show the top ten most active user wallets who have made highest no. of transaction across different user actions.

**c)**    **Compound Lending Pool Assetflow:** this show the flow of DAI over different months in terms of how much its has been borrowed, lent, redeemed etc.

**d)**    **Daily Cashflow Activity:** This visual tracks the daily total amount(DAI) transacted across different user actions.

**e)**     **Unique Wallet addresses:** This visual groups the wallets by $ amount transacted in millions puts them in different categories i.e. <1 M, <2 M etc. This gives count of unique wallets under these categories.

**f)**      **Total Transaction:** provides total number of transactions made based on the filters applied in the report.

**g)**    **Active wallets:** provide total number of unique wallets based on filters applied in the report.

### **2. Tracking Individual wallet address for DAI asset transactions**

Based on above insights (visuals) we can investigate and have further analysis on any wallet behaviors (and this report allowed us to do so). For example, let's choose **one** of the wallets from “top 10 user by $”.&#x20;

Lets pick wallet address “[0xdb7030beb1c07668aa49ea32fbe0282fe8e9d12f](https://etherscan.io/address/0xdb7030beb1c07668aa49ea32fbe0282fe8e9d12f)” for example. Since the PowerBI report visuals are interactive, Once I clicked on that user wallet in "Top 10 Users By $) and it dynamically updated all visual on the page showing data around that user wallet only (shown in screenshot below). As we can see in the screenshot that this user has made total of 39 transactions in H1FY22 and has borrowed total $85.2 M and provided $79.5 M of Liquidity (Mint) in the 6 months.

![Transaction summary of an Individual wallet address](https://lh6.googleusercontent.com/9GjahlbbBLiwL-rtLSsd27msTjFnY3FVGuuQcWmjoAuM9ejAAsPuOydqjOIHYbmNEwfSVB7Kkcbf-vLRHUEqnmC9jMS77i2KP3z48MsLYqcXpHIylZ\_Yo\_Eh6Ab5UHJA6RRsc-Kj)

:bulb:If you closely notice in above screenshot, you can clearly track fluctuation in his Lending and Borrowing contribution in the pool over period of time (in this case, over 6 months)

![](<../.gitbook/assets/image (1) (2).png>)

### **3. Categorization of Depositor/Borrower wallets based on DAI amount supplied**

We could also categorize the wallets based on how much liquidity they provide and see the snapshot of distribution of their share in the liquidity pool. Referring to the screenshot below, we can clearly see how many unique wallets fall under different categories (i.e. under 1M, under 2M, under 3M etc.) in terms of their liquidity pool contribution each month. This also gives insight on how many powerful LPs are acting in the pool.

![Matrix showing unique wallet count distribution of Depositors under different $ value categories](https://lh6.googleusercontent.com/G4uRWpC0BuqWi\_o4LYe2QXdAAK2rFry89NyGNgjJv-ENT7vYrfD-X-9lXrBnbHeJWTpU0GcwRw-2cGHp2PhIKt3p3cktvudVXvwYu3hGgvpVogTUcyd1pwz0am6QS4SYlI0MHiQR)



## **AAVE v2 Protocol Data Analysis**

Similar to Compound transactional data we also analyzed AAVE v2 protocol data and came up with similar analytical insights. Below are the similar (as for Compound above) snapshots for USDC asset transactions on AAVE V2 Protocol.

### **1. Overall Lending pool usage summary for USDC asset**

Below screenshot shows the overall usage summary around USDC and different user actions i.e. lending (aka Deposit), borrowing, repaying etc.

![USDC pool Transaction Summary (AAVE v2 Protocol)](https://lh4.googleusercontent.com/13XfwWxqWA5Dl85vCKTkybZFwYJpZLklF9r5Xue0UZyT6L-07xBCAsutqQUufn-EJ50N\_RsN\_qbMuHRyWsbnpXxZuvMdzCPYiq4YBwwdw7d7Hf7DO5NVo\_jvp2LyIchFvLbzQ9wC)

Summary of different visuals in the above screenshot is the same as mentioned under the Compound protocol section.

### **2. Tracking Individual wallet address for USDC asset transactions**

As we did for compound data visuals, we pick wallet address “[0x3ddfa8ec3052539b6c9549f12cea2c295cff5296](https://etherscan.io/address/0x3ddfa8ec3052539b6c9549f12cea2c295cff5296)” (as shown in screenshot below). As we can see in the screenshot that this user has made a total of 99 transactions in H1FY22 and has been depositing and borrowing in above Billions of $ over the months. **** Interestingly, this wallet user turned out to be [Justin Sun](https://twitter.com/justinsuntron) (not very surprising:stuck\_out\_tongue\_winking\_eye:).

![Transaction summary of an Individual wallet address](https://lh3.googleusercontent.com/lO0kXHvQVsibKtxT2Kw80AKB2cerYWTFgrkY7J3TsJsIgbNebQsG-iIUjv2S1nJq8HSBUAZGYa-A98JvzmfWv3JDwYwkpofn8DscXQzSERersvODGQa5HbHmKC18O9Ct6d4B\_sN1)

:bulb:Notice how Justin's Borrow and Lending contribution in the pool if fluctuating over these month. This gives a good example how we can easily track any borrower and lenders activities over the period of time and can corelated with Overall Market events.

![](<../.gitbook/assets/image (2) (1).png>)

### **2. Categorization of Depositor/Borrower wallets based on UDSC amount supplied**

As we saw in case of DAI for compound, similar insights we can see for USDC as in how many unique wallets are falling under different categories (i.e. under 1M, under 2M, under 3M etc.) in terms of their liquidity pool contribution each month.

![Matrix showing unique wallet count distribution of Depositors under different $ value categories](https://lh5.googleusercontent.com/S272KYsCV13cHrv3G1uquol9C\_nQrH0DFP74qdeZqE81Q\_2BnmVY6Xq3WXcCTQVlCh-AnW1DSwiyCL7jqaaHCjFu2AusXVI9bon\_a7ul8GueKR1awScHclqZmuPrFCmvp6WA-mXS)

****

## **Conclusion:**

As we saw in the example above, we can fetch the on-chain data for other lending protocols similarly and build data insights to track the various dimensions of Wallet behavior and overall asset fluctuations in deposits and loans portfolios. This can give us a base to define relevant Liquidity and Credit related metrics, data-driven decision making in treasury management, and DeFi products pricing, customize them based on wallet behavior and track these metrics regularly.



### **Contributors**

| Discord Handle  | ETH Address                                | Reward           | Version History  |
| --------------- | ------------------------------------------ | ---------------- | ---------------- |
| CrypticPun#1697 | 0x05Fe7045E0A28949C2ee33a331Ad4605DE455F95 | 0 CMK (internal) | Original version |

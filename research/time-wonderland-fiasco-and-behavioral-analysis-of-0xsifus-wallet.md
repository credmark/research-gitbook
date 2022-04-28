# 🚀 Time-Wonderland Fiasco and Behavioral Analysis of 0xSifu’s Wallet

## **Executive Summary:**

This article gives a brief overview of the Time-Wonderland incident and aims to analyze  wallet transactions of  the user known as 0xSifu  who was at the centerstage of this incident.

## **Introduction**

End of January 2022 came with a shock for DeFi community (or for “[**Frog Nation**](https://medium.com/the-defi-wonderland/frog-nation-abracadabra-and-wonderland-united-front-276cb0d723ab)” to be precise) when DeFi protocol Wonderland Treasury Head, also known as Sifu or 0xSifu turned out to be QuadrigaCX’s co-founder Michael Patryn. Interestingly, the Co-Founder Daniel Sestagalli (aka Dani) knew about him beforehand but chose to hide this information from Investors. Expectedly, the investors did not like this and wMEMOs were sold off even way below its backing price at that time. Since Dani is co-founder of Abaracadabra.Money , inevitably, Magic Internet Money aka MIM (Abracadabra stable coin) felt the heat and that heat was cascaded to UST because of investors/traders implementation of [**DegenBox**](https://medium.com/abracadabra-money/our-ust-strategy-the-first-application-of-the-magic-potentialities-of-degenbox-ea35f13d6b5e) strategy. Both Stable coins broke their peg briefly but stabilized quickly.

As per a statement by Dani on [**twitter**](https://twitter.com/danielesesta/status/1486591436233404421), he inferred that he wanted to give 0xSifu a second chance and should not be judged by his early mistake and past actions.&#x20;

So, we thought of investigating his current actions by analyzing publicly available on-chain data information. To start with our analysis, we needed wallet address(s) linked to him.

&#x20;Based on [**information**](https://pro.nansen.ai/wallet-profiler?address=0x5dd596c901987a2b28c38a9c1dfbf86fffc15d77) available on the internet we found out that the wallet address “[_0x5dd596c901987a2b28c38a9c1dfbf86fffc15d77_](https://etherscan.io/address/0x5dd596c901987a2b28c38a9c1dfbf86fffc15d77)” is linked with Michael Patryn (0xSifu).&#x20;

Hereafter, in this article, we are going to analyze his transaction activities linked with this wallet and try to see any unusual behavior(pattern) during the Wonderland fiasco timeline.



## **Time Wonderland incident timeline and correlation with 0xSifu’s wallet activity**

### &#x20;**1. Activities before the news broke out:**

When we checked data on token balances for this wallet address, we saw one interesting insight that he received an unusual amount of MIM tokens in his wallet. Which moved his wallet balance from 3M to 55 M worth of MIM. Notice the time frame (UTC) 24-Jan’22 2:44 PM to 26-Jan’22 5:23 AM in the graph below. We could not pinpoint to any valid reason for this activity based on publicly available information.

![0xSifu's MIM balance tracking graph based on ETH mainnet blockchain data](https://lh6.googleusercontent.com/DWu3mz-olb5Dep9oL8SPHRfmE6-d7OO7dV0Lfnj\_IxyKTF7aDNVLd6RnCfiw\_JinWCfq3LGFYh4Ihzt1qdy5kzlhJeIs6MnxDFWYnQBHcwmhOfdZH62fmqrOMYaNPOzAOfjIxQb6)

### **2. Activities when the news broke out**

At “26 Jan’22 6:47 PM UTC” when @zachxbt shared this tweet about Sifu allegedly revealing his identity. Eventually just around same day when Zach found about his identity, we could see some unusual balance shuffling for his TIME and wMEMO holding on Avalanche network in graphs below (Source: Nansen.ai )

![](https://lh4.googleusercontent.com/T4s9jj-Lyy4-M\_mcn-QYnbVQLSd9DoTGLZtuwAJGsBgfmAGvzrXKeYrbL7bGc5LwI-g-7zOZB\_eU9U6JyZxEPPiyHEJzxVvWJ9o5gHRR7IDo1R1UnwAegC5zX06b-W\_fm4hO5fj8)

![](https://lh5.googleusercontent.com/\_IAVxpTxj9CgOT5mhbViAWhmingGHeEN2nWMWKsHXWoQeYxVBFax95Q9ZTGeVo1yXao6teqprbgwMJb4pXtGqB34UoIsf71SX4axEObrF1-GzuQPM1HCKVtxh7Aiei8jlsJ6pwAD)

### **3. Activities after the news broke out:**&#x20;

Since 0xsifu was officially voted out by [**community vote**](https://snapshot.org/#/bestfork.eth/proposal/0x8f974b76d4f50ea26a1f44843dcda2e0f6a4736883968b29996d272b86b447a9), we could see heighted activity in this wallet’s eth holdings. Notice in the graphs (from Etherscan.io) below how he started moving his ETH funds from some other wallet and then moving them out in chunks in subsequent days.

![ETH inflow and outflow for Sifu's wallet](https://lh3.googleusercontent.com/LCkEDqfTF0ufim2Fgl06SvPjfslr1WWBxBryRkPtHCafUnWgxYdvpYwX7TpY\_0ia56YPcoMDfdI8KU5WhECOx-3NGQy0AZupbB8bMr6gXn6z\_7qJO5orglt7uBi93HcstwToQ2Sm)

![Zooming in the last graph to the timelines around Time-wonderland incident](https://lh5.googleusercontent.com/OQ364pi\_0mCL7VoJdHV8NQCXvZaVN0Ffw6P6JVTP2iqMrn7ZR6R7kMFyvjvPu5n57ZcENrm3wQdgDoVAaS2IAZLgq22RbNNGCBiUUFOJT3aQmz1Ow7O3oxWh8Fr7e8Zf9INoRtB0)

Interestingly, he was moving these funds to Tornado cash to disallow further tracking of his funds.:thinking:

![](https://lh4.googleusercontent.com/6ttyZGvC3wcXFg4Q8BGiRuQoRCAYE6qdQwh7WhKLKguxVTVH\_LHlhMjf7MEUJGOeUh37VM7860fNhJtZCkA3etuiu73nc2SRnDpj2L2Lu8RguWbnHempu7UI7Q8PPfJlIP1Nvoxm)

## **Conclusion**

Looking at this wallet transaction behavior during the above mentioned timeline is definitely not usual behavior and raises questions. More In-depth analysis of the on-chain data can provide more insights around his fund movements across different blockchain. Moreover, this analysis proves how we can find more valuable insights of user behavior patterns by digging up the wallet transactional data and corresponding them to real-life market events.

## **Contributors**

| Discord Handle  | ETH Address                                | Reward           | Version History  |
| --------------- | ------------------------------------------ | ---------------- | ---------------- |
| CrypticPun#1697 | 0x05Fe7045E0A28949C2ee33a331Ad4605DE455F95 | 0 CMK (internal) | Original version |

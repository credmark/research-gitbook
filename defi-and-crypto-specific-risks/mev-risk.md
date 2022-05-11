# MEV risk

MEV stands for Maximal Extractable Value or in the past often for Miner Extractable Value. Originally, MEV refers to the profit a block producer (so a miner, sequencer, validator, etc...) can make by including, excluding, or rearranging transactions in the blocks they produce \[1].

The MEV risks is based on the fact, that every transactions is first submitted to the so-called Mempool (or Memory pool), which is a database of unconfirmed transactions. As soon as a miner (or validator, ...) picks up a transaction and includes it into a block, the transaction is removed from the Mempool \[2].

Nowadays, the risks of MEV occur as they are not only the miners active in the Mempool, but instead active and independent network participants, that "run complex algorithms on blockchain data to detect profitable MEV opportunities and have bots to automatically submit those profitable transactions to the network." \[3]

There exist certain specific MEV opportunities, that these so-called "searches" look for \[3]:

* DEX Arbitrage, so finding price differences between DEXs for the same token pair
* Liquidations, so liquidating collateral that was used for lending positions
* Sandwich trading, so front running large trades that move the price of a certain trading pair and selling with a higher price after the large transactions was processed
* NFT MEV, so front running popular NFT drops or automatically buy NFTs that were listed below floor price mistakenly

As of May 2022, MEV accounts for more than $620m. You can find a Dashboard, that illustrates the total MEV [here](https://explore.flashbots.net).

But MEV is not only bad at all. In general, it is a way of fixing economic inefficiencies, thus helping the ecosystem to become more robust. On the other side, the user experience can be really bad, especially when being sandwiched or when several front runners compete with high gas prices for their transaction to be included in the next block and thus resulting in network congestion and high gas prices for everyone else \[3].

## &#x20;References

1. Cowswap, [https://cowswap.exchange/#/faq?chain=mainnet](https://cowswap.exchange/#/faq?chain=mainnet)
2. River, [https://river.com/learn/terms/m/mempool/](https://river.com/learn/terms/m/mempool/)
3. Ethereum Org, [https://ethereum.org/en/developers/docs/mev/](https://ethereum.org/en/developers/docs/mev/)
4. MEV Explore, [https://explore.flashbots.net](https://explore.flashbots.net)

## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

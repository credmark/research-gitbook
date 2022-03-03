# Market Data Issues and Techniques

## Executive Summary

1. The on-chain market data is raw and it needs to be checked and cleaned to be used for models.
2. Issues with on-chain market data: 1) data from blockchain is that they are discretized in block and time. On-chain data's timestamp is different from more real-time data like API/Oracle's timestamp. 2) data from blockchain is subject to large jump that needs interpretation and proper handling. 3) data needs audit.
3. The way to address the issues is to employ data techniques to provide data fit to the use of various models.

## Some Food for Thoughts

The ETH blockchain has grown to a whooping 500G (Full node sync) or 10T (full archive node sync), as of 25th Feb 2022 (\[1]). Our journey of exploring the on-chain data just got started. Below items are thoughts in the start. They do not meant to be exhaustive for now but some fundamental ideas that drive the design of the risk system.

The use of blockchain in the center of the DeFi as a distributed ledger records all transaction/event publicly on-chain. The blockchain, as a data structure, records batch of transaction/event in blocks and validated by the miners with PoW (or validators in the PoS). The transaction is stamped with the time when the block was created. On an average day, it takes anywhere **between 15 seconds and 5 minutes** to process a transaction if you pay the standard gas price (see [on-chain-gas-fees-eth.md](on-chain-gas-fees-eth.md "mention")). It's also expected that the block creation time is little manipulated, though network congestion could delay of it. The first point is that, **data from blockchain is that they are discretized in block and time. On-chain data's timestamp is different from more real-time data like API/Oracle's timestamp.**

The second point, an innovation in DeFi, is the use of smart contract to bundle several traditional transactions together, such as flash loan and flash swap This created a "wormhole-warp" within one transaction that increase/decrease tokens holdings with different smart contracts. Adding the manifested high volatility in BTC/ETH/token prices, **data from blockchain is subject to large jump that needs interpretation and proper handling.**

The third point is that **data needs audit**. In TradeFi, the balance is obtained from input of the transactions. In DeFi, the balance of the current holding is a global state of the account, while all transactions leading to the current balance is subject to the ETL process of the blockchain. The history need to be replayed to restore the process. Could that balance at some past point of time be negative? That's impossible by the rule of the blockchain but it could be caused due to mishaps in the ETL process of the contract.

The ways to address above issues is to employ techniques to provide data fit to the be used in various models.

After inking the thoughts, below we describe the specifications to get started.

## Specification

* Input Time: given a period, i.e. min, sec, day, or OHLC (Open, High, Low, Close) versions of these periods, supply the series of price of a list of tokens. There is a global and per token setting for the day snapping time.
* Checks:
  * Missing
  * Staleness - same value for 4 consecutive days
  * Filtering by liquidity and tradeability: was any trade on this price? Is the trade volume sufficient for general liquidity?
  * Outlier detection
* Cleaning:
  * Missing data backfilling method: use previous data point, or proxy choice
  * Alignment: use the last available data point, or using missing data backfilling method
  * Outlier removal or keep (dangerous)

## Examples

Take wallet address 0x15abb..., we obtain the Transfer event log of an ERC-20 token for the account and use the data from the last block of the day as the balance of the day. There is a gap between 2/18 and 2/22 when the address had no activity of this token.&#x20;

| Balance         | Time                  |
| --------------- | --------------------- |
| 199382952199581 | 2/22/2022 9:58:13 PM  |
| 224363756439581 | 2/18/2022 10:15:07 PM |

When we want to use this data as a time series, the backfilling strategy is to fill it backwardly, i.e. use the last available balance in time to fill the it's future time till a new transaction is done. In such way, we obtain below data.

| Balance         | Date | Last Done Time (was Time) |
| --------------- | ---- | ------------------------- |
| 199382952199581 | 2/22 | 2/22/2022 9:58:13 PM      |
| 224363756439581 | 2/21 | 2/18/2022 10:15:07 PM     |
| 224363756439581 | 2/20 | 2/18/2022 10:15:07 PM     |
| 224363756439581 | 2/19 | 2/18/2022 10:15:07 PM     |
| 224363756439581 | 2/18 | 2/18/2022 10:15:07 PM     |

To visualize, below figure shows the the change of the balance from Apr 2021 to Feb 2022. Note the balance has reached negative because it is restored from Transfer event logs only (this reminds us the importance of **data audit**).&#x20;

![Account balance change for an ERC-20 token in 0x15abb... from Apr 2021 to Feb 2022. Incorrect due to empty values (See above for the note on the negative balance)](<../../../.gitbook/assets/image (3) (1) (1).png>)

As we apply this backfilling method to the history from Apr 2021 to Feb 2022, we obtain below figure. The sharp edges in above figure (due to empty value) has changed to flat-jump form (backfilled). This is the expected behavior of an wallet when there is no transaction.

![Account balance change for an ERC-20 token in 0x15abb... from Apr 2021 to Feb 2022. Backfilled. (See above for the note on the negative balance)](<../../../.gitbook/assets/image (8) (1) (1) (1).png>)

There will be more examples in dealing with various types of data. We will enrich this WIP (Work-in-progress) article.

## Reference



\[1] EtherScan.io: [https://etherscan.io/chartsync/chaindefault](https://etherscan.io/chartsync/chaindefault) and [https://etherscan.io/chartsync/chainarchive](https://etherscan.io/chartsync/chainarchive).



## Contributors <a href="#contributors" id="contributors"></a>

| Discord Handle | ETH address                                 | Reward          | Contribution     |
| -------------- | ------------------------------------------- | --------------- | ---------------- |
| ​kunlun#8324   | 0x109B3C39d675A2FF16354E116d080B94d238a7c90 | $CMK (internal) | Original version |

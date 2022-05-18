# Arbitrum

[Arbitrum](https://arbitrum.io/) is a Layer 2 scaling solution created by Offchain Labs, and officially launched in August 2021. It makes use of so-called optimistic rollups and settles transaction in batches to the Ethereum main chain \[1].

Arbitrum claims to be capable of processing 40,000 transactions per second (Ethereum can handle 14) while fully supporting the Ethereum Virtual Machine (EVM) \[2]. Thus, any DeFi application can be simply bridged to Arbitrum, and [many have done so already](https://portal.arbitrum.one/).&#x20;

The current [TVL](https://docs.credmark.com/credmark-wiki/glossary#tvl) of Arbitrum as of May 2022 is roughly USD 2B. The current numbers can be found [here](https://defillama.com/chain/Arbitrum) \[3].

### How does Arbitrum work?

Following the [Arbitrum Developer Documentation](https://developer.offchainlabs.com/docs/inside\_arbitrum), at the most basic level level, the chain works like that:

![](<../../.gitbook/assets/Bildschirmfoto 2022-05-03 um 22.17.25.png>)

"If you want an Arbitrum chain to process a transaction for you, you need to put that transaction into the chain’s inbox. Then the chain will see your transaction, execute it, and produce some outputs: a transaction receipt, and any withdrawals that your transaction did." \[4]

Arbitrum is a so-called Optimistic Rollup. A rollup means, that all the messages that are put into the inbox by users, are recorded  on the Ethereum main chain as calldata. "Because of this, everyone has the information they would need to determine the current correct state of the chain -- they have the full history of the inbox, and the results are uniquely determined by the inbox history, so they can reconstruct the state of the chain based only on public information, if needed." \[4]

The "optimistic" part refers to the fact, "that Arbitrum advances the state of its chain by letting any party (a “validator”) post a rollup block that that party claims is correct, and then giving everyone else a chance to challenge that claim." \[4]

There is a great article by Offchain Labs giving more insights into Optimistic Rollups here:

{% embed url="https://medium.com/offchainlabs/optimistic-rollups-the-present-and-future-of-ethereum-scaling-60fb9067ae87" %}

### How to use Arbitrum?

As Arbitrum is EVM-compatible, it is possible to use the chain directly through a decentralized application like [Aave](../../protocol-layer/lending/aave.md), or [Sushiswap](../../protocol-layer/dexes/sushiswap.md). Nevertheless, you need to move funds to the Arbitrum network first, either by using the [Arbitrum bridge](https://bridge.arbitrum.io/) or a [third party solution](../bridges/).

### Chain Info

The core information about the Arbitrum chain can be derived from the [Offchain Labs Dev Center](https://developer.offchainlabs.com/docs/mainnet):

Name: **Arbitrum One**

ChainID: **42161**

Currency Symbol: **ETH**

Public RPC Endpoints:

* Offchain Labs: [**https://arb1.arbitrum.io/rpc**](https://arb1.arbitrum.io/rpc)
* Infura: [**https://arbitrum-mainnet.infura.io/v3/YOUR-PROJECT-ID**](https://infura.io/docs/ethereum#section/Choose-a-Network)
* Alchemy: [**https://arb-mainnet.g.alchemy.com/v2/your-api-key**](https://docs.alchemy.com/alchemy/apis/arbitrum)

### Risk Summary

Our friends from [L2beat](https://l2beat.com/) offer a great summary of the associated risks of the [Arbitrum project](https://l2beat.com/projects/arbitrum/) \[5]:

**Funds can be stolen if…**

* none of the whitelisted verifiers checks the published state. Fraud proofs assume at least one honest and able validator **(CRITICAL)**,
* a contract receives a malicious code upgrade. There is no delay on code upgrades **(CRITICAL)**.

**Funds can be lost if…**

* there are mistakes in the highly complex AVM implementation.

**Funds can be frozen if…**

* the centralized validator goes down. Users cannot produce blocks themselves and exiting the system requires new block production **(CRITICAL)**.

****[**MEV**](https://docs.credmark.com/dealing-with-risks/defi-and-crypto-specific-risks/mev-risk) **can be extracted if…**

* the operator exploits their centralized position and frontruns user transactions.

## References

1. The Block, [https://www.theblockcrypto.com/post/116148/ethereum-scaling-solution-arbitrum-launches-mainnet-raises-120-million-funding](https://www.theblockcrypto.com/post/116148/ethereum-scaling-solution-arbitrum-launches-mainnet-raises-120-million-funding)
2. Decrypt, [https://decrypt.co/resources/what-is-arbitrum-speeding-up-ethereum-using-optimistic-rollups](https://decrypt.co/resources/what-is-arbitrum-speeding-up-ethereum-using-optimistic-rollups)
3. DeFi Llama, [https://defillama.com/chain/Arbitrum](https://defillama.com/chain/Arbitrum)
4. Offchain Labs Dev Center, [https://developer.offchainlabs.com/docs/inside\_arbitrum](https://developer.offchainlabs.com/docs/inside\_arbitrum)
5. L2beat, [https://l2beat.com/projects/arbitrum/](https://l2beat.com/projects/arbitrum/)

## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

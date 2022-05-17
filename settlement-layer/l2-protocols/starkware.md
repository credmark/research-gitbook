# StarkWare

StarkWare is a software company focused on delivering scaling solutions for the Ethereum blockchain. They provide two major products in StarkNet and StarkEx.&#x20;

The term [STARK](https://twitter.com/lucasdantur/status/1524572444866056193) refers to **S**calable **T**ransparent **AR**gument of **K**nowledge \[1].

StarkEx was launched on Mainnet in June 2020 and is offering a standalone [ZK-Rollup](https://docs.credmark.com/credmark-wiki/glossary#zero-knowledge-rollups-zk-rollups) SaaS architecture for several use cases like NFT minting & trading, derivative trading as well as AMM and spot trading. It is used by [dydx](../../protocol-layer/derivatives-and-options/dydx.md), sorare or [Immutable](immutable-x.md) to power their decentralized applications \[2]. There is no composability and each app is encapsulated \[3].

StarkNet is still in the Alpha phase on the Testnet and represents a permissionless decentralized ZK-Rollup with composability. They recently launched their so-called StarkGATE token [bridge](../bridges/) to allow ETH transfers from Ethereum to StarkNet \[3].

Moreover, StarkWare introduced their own programming language [Cairo](https://www.cairo-lang.org/docs/) that powers StarkEx and is used as the native smart contract language for StarkNet.

### How does StarEx work?

As mentioned before, StarkEx is a service provided to Dapps and offers its customers to build their own business logic while running on the StarkEx Service \[4]:

![](<../../.gitbook/assets/Bildschirmfoto 2022-05-17 um 16.56.41.png>)

In simple terms, there are 4 steps \[2]:

1. Batching of user transactions off-chain and sending to StarkEx Service
2. Validation of Transactions and Update of relevant balances
3. Generating a STARK proof attesting validity of the transactions in the batch and send proof on-chain
4. On-chain verifier smart contract receives and verifies the proof and new balances are stored on-chain

### How to use StarkEx?

The following Dapps run on StarkEx - so by using them you will use StarkEx technology:

* [dydx](https://dydx.exchange/) - perpetual swap trading
* [sorare](https://sorare.com/) - football trading cards
* [Immutable](https://www.immutable.com/) - NFT marketplace
* [DeversiFi ](https://deversifi.com/)- spot trading
* [Celer](https://www.celer.network/) - blockchain interoperability&#x20;

Moreover, there is a StartkEx playground available [here](https://docs.starkware.co/starkex-playground-tutorial/).

### How does StarkNet work?

StarkNet is a permissionless decentralized ZK-Rollup operating as an L2 network over Ethereum.&#x20;

"The StarkNet node (called sequencer) is implemented in Python. The StarkNet transaction execution environment, called StarkNet OS (similar to the Ethereum Virtual Machine), is implemented in Cairo. This optimizes the proving performance of each transaction execution. A Solidity contract deployed on Ethereum connects the StarkNet network (L2) to Ethereum (L1)." \[5]

The details on the technical docs can be found [here](https://starknet.io/building-on-starknet/).

### How to use StarkNet?

As mentioned before, StarkNet is still in the Alpha phase, thus currently only the StarkGate bridge is active on Mainnet:&#x20;

{% embed url="https://starkgate.starknet.io/" %}

On the Testnet, there exist various protocols to play around with. Be aware that you need to set up Argent X as Browser Wallet to make use of StarkNet.

{% embed url="https://www.argent.xyz/argent-x/" %}

{% embed url="https://starkswap.notion.site/Setting-Up-Argent-29cab2b96ec34908b0eb8ca9d495a4f4" %}

Some of the existing applications are AMMs like Starkswap and Jediswap:

{% embed url="https://www.starkswap.co/app/faucet" %}

{% embed url="https://app.testnet.jediswap.xyz/#/swap" %}

FInally, there is the NFT marketplace Oasis to play around with:

{% embed url="https://testnet.playoasis.xyz/" %}

## References

1. Starkware, [https://starkware.co/stark/](https://starkware.co/stark/)
2. Starkware, [https://starkware.co/starkex/](https://starkware.co/starkex/)
3. Lucas Dantur, [https://twitter.com/lucasdantur/status/1524572444866056193](https://twitter.com/lucasdantur/status/1524572444866056193)
4. StarkEx V4, [https://docs.starkware.co/starkex-v4/overview](https://docs.starkware.co/starkex-v4/overview)
5. StarkWare Tech Stack, [https://starkware.co/tech-stack/](https://starkware.co/tech-stack/)

## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

# Optimism

Optimism is a [Layer 2 ](https://docs.credmark.com/credmark-wiki/glossary#layer-1-layer-2)scaling solution developed by the Optimism Foundation to promote growth and sustainability of public goods \[1]. The open Mainnet launch was in December 2021. In spring 2022 Optimism reached a max of over $700m in [TVL](https://docs.credmark.com/credmark-wiki/glossary#tvl), current numbers can be found [here](https://l2beat.com/projects/optimism/) \[2].

### How does Optimism work?

As [Arbitrum](arbitrum.md), Optimism is using optimistic rollups to batch single transactions and then these rollups are submitted to the Ethereum Mainchain. "Unless a user submits their transaction directly to the [Canonical Transaction Chain](https://community.optimism.io/docs/protocol/compressed-ctc/), new blocks are produced by something called a sequencer. This sequencer instantly confirms valid transactions, then creates and executes blocks on Optimism’s layer 2—a blockchain that sits atop the L1 blockchain, in this case Ethereum." \[3]

The High Level Architecture of Optimism can be found here \[4]:

{% embed url="https://community.optimism.io/docs/protocol/protocol-2.0/#system-overview&gid=1&pid=1" %}

### How to use Optimism?

As Optimism is EVM-compatible, it is possible to use the chain directly through a decentralized application like [Aave](../../protocol-layer/lending/aave.md), or [Uniswap](../../protocol-layer/dexes/uniswap-v3.md). Nevertheless, you need to move funds to the Optimism network first, either by using the [Optimism bridge](https://app.optimism.io/bridge) or a [third party solution](../bridges/).

### Chain Info

The core information about the Optimism chain can be derived from the [Optimism Docs](https://community.optimism.io/docs/useful-tools/networks/#optimism-mainnet)\[5]:

Name: **Optimism**

ChainID: **10**

Public RPC Endpoints:

* HTTP endpoint: [**https://mainnet.optimism.io/**](https://mainnet.optimism.io/)****
* WebSocket: **** [**wss://ws-mainnet.optimism.io/**](wss://ws-mainnet.optimism.io/)****
* Infura: https://optimism-mainnet.infura.io/v3/\<Infura Project ID>
* Alchemy: https://opt-mainnet.g.alchemy.com/v2/your-api-key

Canonical Transaction Chain: [0x5E4e65926BA27467555EB562121fac00D24E9dD2](https://etherscan.io/address/0x5E4e65926BA27467555EB562121fac00D24E9dD2)

### Risk Summary

Our friends from [L2beat](https://l2beat.com/) offer a great summary of the associated risks of the [Optimism project](https://l2beat.com/projects/optimism/) \[2]:

**Funds can be stolen, if...**

* an invalid state root is submitted to the system **(CRITICAL)**,
* a contract receives a malicious code upgrade. There is no delay on code upgrades **(CRITICAL)**.

**Funds can be frozen, if...**

* the centralized validator goes down. Users cannot produce blocks themselves and exiting the system requires new block production **(CRITICAL)**.

****[**MEV**](https://docs.credmark.com/dealing-with-risks/defi-and-crypto-specific-risks/mev-risk) **can be extracted if…**

* the operator exploits their centralized position and frontruns user transactions.

### The Optimism Token

Optimism announced their Token end of April 2022 but as well introduced a new model of governance for the protocol. Instead of only having one governance token, there will be two co-equal chambers, namely the Token House and the Citizens´House \[6]:

![](<../../.gitbook/assets/Bildschirmfoto 2022-05-18 um 12.28.13.png>)

The airdrop announcement for OP-Token is only for the Token House, while there will be an additional airdrop for the Citizen\`s House in form of so-called soulbound NFTs, that are not transferable.&#x20;

To check your airdrop eligibility, please visit this [site](https://app.optimism.io/governance).

## References

1. Optimism, [https://www.optimism.io/about](https://www.optimism.io/about)
2. L2 beat, [https://l2beat.com/projects/optimism/](https://l2beat.com/projects/optimism/)
3. Decrypt, [https://decrypt.co/resources/what-is-optimism-using-rollups-to-help-scale-ethereum](https://decrypt.co/resources/what-is-optimism-using-rollups-to-help-scale-ethereum)
4. Optimism Docs, [https://community.optimism.io/docs/protocol/protocol-2.0/#introduction\&gid=1\&pid=1](https://community.optimism.io/docs/protocol/protocol-2.0/#introduction\&gid=1\&pid=1)
5. Optimism Docs, [https://community.optimism.io/docs/useful-tools/networks/#](https://community.optimism.io/docs/useful-tools/networks/)
6. Optimism Docs, [https://community.optimism.io/docs/governance/](https://community.optimism.io/docs/governance/)

## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

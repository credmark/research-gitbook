# Boba Network

The Boba Network is an Ethereum-scaling solution, launched by the OMG Foundation in Sept. 2021 and is based on the publicly available, open-sourced Optimism codebase \[1]. The project introduced a [governance token](../../asset-layer/governance-token.md) ($BOBA) with the launch, which will be the basis for voting on the Boba DAO.&#x20;

Moreover, "BOBA tokens staked on Boba Network will also receive a portion of the transaction fees earned by the network through an on-chain distribution governed by the community." \[1]

After its peak in Dec 2021 with over $600m TVL, these numbers have been crushed with TVL currently sitting at roughly $60m. The actual numbers can be found [here](https://defillama.com/chain/Boba) \[2].

### How does Boba Network work?

The Boba Network is build on the Optimistic Rollup solution and "lives _inside_ of Ethereum as a series of smart contracts that are capable of executing Ethereum transactions." \[3]

![](<../../.gitbook/assets/Bildschirmfoto 2022-05-06 um 16.48.55.png>)

While Boba Network is built upon [Optimism](optimism.md), there are still some key differences \[4]:

* providing additional cross-chain messaging such as a `message-relayer-fast`
* using different gas pricing logic
* providing a swap-based system for rapid L2->L1 exits (without the 7 day delay)
* providing a community fraud-detector that allows transactions to be independently verified by anyone
* interacting with L2 ETH using the normal ETH methods (`msg.value`, `send eth_sendTransaction`, and `provider.getBalance(address)` rather than as WETH
* being organized as a [DAO](https://forum.boba.network)
* native [NFT bridging](https://docs.boba.network/other/bridges)
* automatically relaying classical 7-day exit messages to L1 for you, rather than this being a separate step

### How to use Boba Network?

As Boba is EVM-compatible, it is possible to use the chain directly through a decentralized application like [Autofarm](https://autofarm.network/boba/). Nevertheless, you need to move funds to the Boba network first, either by using the [Boba bridge](https://gateway.boba.network) or a [third party solution](../bridges/) like [Across Protocol](https://across.to) or [Connext](https://bridge.connext.network).

### Chain Info

The core information about the Arbitrum chain can be derived from the [Boba Developer Docs](https://docs.boba.network/user-documentation/001\_how-to-bridge):

Name: **BOBA L2**

ChainID: **288**

Currency Symbol: **ETH**

Public RPC Endpoints:

* **Boba Mainnet**: [**https://mainnet.boba.network**](https://mainnet.boba.network)****
* **Block explorer:** [**https://blockexplorer.boba.network/**](https://blockexplorer.boba.network)****

### Token Info

Smart Contract address: [0x42bBFa2e77757C645eeaAd1655E0911a7553Efbc](https://etherscan.io/token/0x42bbfa2e77757c645eeaad1655e0911a7553efbc) \[5]

### Risk Summary

Our friends from [L2beat](https://l2beat.com) offer a great summary of the associated risks of the Boba project \[6]:

**Funds can be stolen if…**

* an invalid state root is submitted to the system **(CRITICAL)**,
* a contract receives a malicious code upgrade. There is no delay on code upgrades **(CRITICAL)**.

**Funds can be lost if…**

* there are mistakes in the highly complex OVM implementation.

**Funds can be frozen if…**

* the centralized validator goes down. Users cannot produce blocks themselves and exiting the system requires new block production **(CRITICAL)**.

**MEV can be extracted if…**

* the operator exploits their centralized position and frontruns user transactions.

## References

1. Boba Network, [https://boba.network/public-mainnet/](https://boba.network/public-mainnet/)
2. Defillama, [https://defillama.com/chain/Boba](https://defillama.com/chain/Boba)
3. Boba Developer Docs, [https://docs.boba.network/faq](https://docs.boba.network/faq)
4. Boba Developer Docs, [https://docs.boba.network/](https://docs.boba.network)
5. Etherscan, [https://etherscan.io/token/0x42bbfa2e77757c645eeaad1655e0911a7553efbc](https://etherscan.io/token/0x42bbfa2e77757c645eeaad1655e0911a7553efbc)
6. L2beat, [https://l2beat.com/projects/bobanetwork/](https://l2beat.com/projects/bobanetwork/)



## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

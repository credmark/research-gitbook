# Immutable X

Immutable X is a Layer-2 scaling solution, that was launched in April 2021 while focusing primarily on NFTs.&#x20;

"Through Immutable X, its layer-two scaling solution, Immutable aims to promote mainstream NFT adoption by offering gas-free minting and trading, self custody alongside seamless UX for developers and consumers. Immutable X is also ensuring any NFT activity on the protocol is completely carbon neutral by purchasing carbon credits to offset gas consumed on Ethereum." \[1]

Currently, Immutable is most famous for its trading card game [Gods Unchained](https://godsunchained.com/), and has a [TVL](https://docs.credmark.com/credmark-wiki/glossary#tvl) about roughly $50m. The current numbers can be found [here](https://l2beat.com/projects/immutablex/) \[2].

The Immutable X ecosystem is powered by the [$IMX token](https://www.coingecko.com/en/coins/immutable-x), which is used to pay for fees, take part in governance votes and can be staked to earn a share of the rewards pools.

### How does Immutable X work?

Immutable is build on StarkEx from [Starkware](starkware.md). It is using a technology called Zero-Knowledge rollups (zk-rollups). As other scaling solutions, they combine a large number of individual transactions and submit them in one transaction to the Ethereum mainchain. In contrast to Optimistic rollups, zk-rollups do not assume that every transaction is valid until proven otherwise but instead prove it instantly by using so-called validity proofs \[3].

"Using validity proofs means that once a proof has been accepted on-chain, users have immediate confirmation that those transactions were valid and are now immutable. In an NFT context, this solves both the problems identified with optimistic rollups above: users can withdraw immediately and no-one is able to attack the system, regardless of the amount of funds flowing through the system." \[4]

### How to use Immutable X?

Immutable X positions itself more like a platform for other decentralized applications instead of a sidechain, where the user needs to move funds to in order to use the applications that are build on top of it. Thus, there exists a [third-party marketplace ecosystem](https://market.immutable.com/) that allows user to connect with their existing wallets. To use this marketplace, you are required to [register as a user](https://docs.x.immutable.com/docs/getting-started-guide#register-a-user-account).

### How to build on Immutable X?

To integrate an application into the Immutable X ecosystem, there exists a dedicated SDK to make use of. The detailed guidance can be found [here](https://docs.x.immutable.com/docs/getting-started-guide).

### IMX Token Info

Immutable X has its one token IMX, which serves as [Governance](../../asset-layer/governance-token.md) and [Utility token](../../asset-layer/utility-token.md) within the ecosystem. While the governance is handled via Snapshot votes, the utility for IMX is provided by the fact, that 20 % of the protocol fees for every transaction need to be paid in IMX token. Moreover, these fees are collected in a dedicated rewards pools and shared between all IMX stakers. Additionally, there exist certain Play-To-Earn initiatives to encourage active users of the protocol to get some IMX as rewards \[5].

**Smart Contract address:** [0xF57e7e7C23978C3cAEC3C3548E3D615c346e79fF](https://etherscan.io/token/0xf57e7e7c23978c3caec3c3548e3d615c346e79ff) \[6]

### Risk Summary

Our friends from [L2beat](https://l2beat.com/) offer a great summary of the associated risks of [Immutable X](https://l2beat.com/projects/immutablex/) \[7]:

**Funds can be stolen if...**

* a contract receives a malicious code upgrade. There is a 14 days delay on code upgrades.

**Funds can be lost if...**

* the external data becomes unavailable,
* the proof system is implemented incorrectly.

**Users can be censored if...**

* the committee restricts their access to the external data,
* the operator refuses to include their transactions. They can still exit the system.

****[**MEV**](https://docs.credmark.com/dealing-with-risks/defi-and-crypto-specific-risks/mev-risk) **can be extracted if...**

* the operator exploits their centralized position and frontruns user transactions.

## References

1. Immutable, [https://www.immutable.com/blog/immutable-x-alpha-trading-launch](https://www.immutable.com/blog/immutable-x-alpha-trading-launch)
2. L2 Beat, [https://l2beat.com/projects/immutablex/](https://l2beat.com/projects/immutablex/)
3. Alchemy, [https://www.alchemy.com/blog/zero-knowledge-rollups](https://www.alchemy.com/blog/zero-knowledge-rollups)
4. Immutable X, [https://immutablex.medium.com/eli5-nft-scaling-solutions-b1de4ad82461](https://immutablex.medium.com/eli5-nft-scaling-solutions-b1de4ad82461)
5. Immutable X, [https://www.immutable.com/token](https://www.immutable.com/token)
6. Etherscan, [https://etherscan.io/token/0xf57e7e7c23978c3caec3c3548e3d615c346e79ff](https://etherscan.io/token/0xf57e7e7c23978c3caec3c3548e3d615c346e79ff)
7. L2beat, [https://l2beat.com/projects/immutablex/](https://l2beat.com/projects/immutablex/)



## Contributors

| Discord Handle   | ETH Address     | Reward            | Comments |
| ---------------- | --------------- | ----------------- | -------- |
| Matt \| CMK#9019 | mattropolis.eth | 0 $CMK (internal) | Create   |

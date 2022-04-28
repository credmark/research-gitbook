# Smart Contract Financial Risk

### **Risk Report on IDLE Best Yield Smart contract**

#### **Intro to IDLE Best Yield**

The IDLE v4 (USDT) Best Yield fund is invested in two yield-returning funds: AAVE’s USDT pool and Compound’s USDT pool. According to IDLE’s [documentation](https://developers.idle.finance/strategies/max-yield), the Best Yield fund is allocated by maximizing the following expression for a and c

c\*rcompound(c)+a\*raave(a)

where a is the amount of the Best Yield fund invested in AAVE and c is the amount of the Best Yield fund invested in Compound. The functions rcompound, raave are the yield rates from Compound and AAVE (resp.) which depend on the amount to be invested in each fund. \\

A useful metaphor for understanding how the above optimization shakes out is to imagine IDLE as a very heavy person trying to get off the ground in a group game of see-saw. There may be situations when IDLE can do it by staying entirely on one side (if everyone else is on the other side, for example) but when the participation between the two ends is more or less the same, IDLE has to manage its weight very carefully (so as not to lean too hard on one side and thus drive interest rates way down for itself).

#### **Smart contract for IDLE Best Yield**

The IDLE v4 USDT Best Yield smart contract can be found [here](https://etherscan.io/address/0xf34842d05a1c888ca02769a633df37177415c2f8#readProxyContract). Since the documentation for IDLE is very light on details, we turned to the smart contract to find answers to the following questions. \\

1. What triggers a rebalancing of the IDLE best yield fund?
2. What decides how much of the fund is rebalanced?

Our investigation revealed something very surprising about the IDLE v4 USDT Best Yield smart contract (and there is good evidence that this is the case for all IDLE pool smart contracts).\\

The IDLE v4 USDT Best Yield smart contract has a two step process for rebalancing funds among AAVE and Compound. To explain how it works, let’s take a quick look at some features of the contract.\\

The contract stores as lastAllocations its most recently successfully applied portfolio allocations as a pair of numbers, each representing the percentage of the total fund amount stored in Compound/AAVE. Potential future movements of the fund are stored as lastRebalancerAllocations, which is also a pair of percentages. The function rebalance(), when triggered, compares the contract’s stored lastAllocations with the lastRebalancerAllocations; if there is a difference, the contract executes trades to bring its portfolio into alignment with lastRebalancerAllocations.\\

In order for IDLE to adjust its USDT Best Yield portfolio, (1) the smart contract’s lastRebalancerAllocations must be updated to reflect the new portfolio position, and (2) the rebalance() function must be triggered.\\

The only way to update the smart contract’s lastRebalancerAllocations is via the setAllocations() function. We expected to see something like the [optimization equation](https://docs.google.com/document/d/1YsSozg0HElkiVtlgeAE033FfwzWkFHbVR9Ps1x8-6us/edit#bookmark=id.yuc2h59y31m1) here, and perhaps even find some answers to our motivating [questions](http://link). Instead, what we find is that the setAllocations() function is hard-coded to receive instruction from an Ethereum address the contract refers to as “the Rebalancer”. This address is not a smart contract; it is a private address. This means we cannot see how IDLE is making decisions about how to allocate its funds, including frequency of rebalancing, strategy for allocation, and whether trades are being executed by hand or algorithmically.

#### **Examples**

By watching the Rebalancer’s address, we see that the Rebalancer may setAllocations() for an IDLE fund smart contract and wait a significant period of time before triggering the rebalance() function.

![](https://lh4.googleusercontent.com/et2JR6NhN4QL8yoP2nmZc52YER3FnfGxJGs754T2ohY7NUyDUnbtn2FzRpKaKgRPrn-01GfeEsxK3zkiDfDZBtsJmwyBpKOiQxJ1\_OH5d7RqrqU9ozWFR0zWr-I3huQso0D7S6ie=s0)

![](https://lh6.googleusercontent.com/iIEJd0s\_q6L6-hnEezqIPv3vXS5kLlD\_\_txZlSmXAoxX\_7hSAVOKZMjQZD3TknfsppUlVibb12dp5SAQupr6l6qnIQ0b5zSPwYHC5DzG7euwM9JqHYt9E-7V9PXaiQqlxaXm7Dnv=s0)

Sometimes, the Rebalancer will not rebalance() the new lastRebalancerAllocations at all, and setAllocations() again before triggering rebalance().\\

***

![](https://lh5.googleusercontent.com/GAbBGR27uy414ziPQsUmS8Kexm0lz1zxjhyWDG5DkgQ6ZKmhfpD2V31dd0XuNaeO0A9oulmAlZck\_YvjS74Z8nZ9-QT-\_-EOYOY5e\_xneUnJQ3cGo671Fifxy0gRbM-FPxhPIspl=s0)

#### **Inherent Risks**

**Trust**

Inherent in the Rebalancer strategy that IDLE has deployed in its smart contracts is the need for trust: users must trust that IDLE is actually following the protocol described in their documentation, as whatever allocation-management strategy they are deploying is not on-chain.\\

**Announcing their next moves**

Another element of risk in the Rebalancer strategy is that every call to setAllocations() by the Rebalancer is public. This means that before IDLE can re-allocate its funds, it first announces to the entire blockchain exactly how it plans to do that.\\

***

**Public access to rebalance()**

While the setAllocations() function is restricted to the Rebalancer, the rebalance() function is publicly executable by anyone willing to pay the gas. This means there may be instances where IDLE has setAllocations(), decides not to rebalance(), but a third-party may trigger that rebalancing of funds if it serves them.

**Risk Mitigation**

The rebalance() function does have a built-in “pause” function, so that if it is being used maliciously by someone outside of IDLE, the function can be paused and IDLE funds will cease being moveable via this publicly accessible function.

# Protocol Risk

Protocol risk, in traditional terms, is the risk associated with product liability.  Product liability claims are the result of product failure that, arguably, causes harm.&#x20;

Fortunately, DeFi and other crypto products can cause great harm. That wouldn't be the case if they were frivolous. Unfortunately, for people/companies/DAOs writing and publishing these protocols, badly injured parties often seek compensation.&#x20;

\[Note that protocols are collections of smart contracts.]

## Bad Code (Bugs)

At a very high level, we consider two type of bugs:

1. Conceptual bugs (intention), and
2. Implementation bugs.

When people talk about software bugs they normally only mean "implementation bugs", but conceptual bugs (also the result of flawed logic) are just as pervasive and just as damaging.

### Conceptual Bugs

Conceptual bugs fall along a spectrum, from nefarious intent to dumb idea.

Plenty of protocols have been designed with the intention of stealing people's money in more or less obvious ways. People who do this should be sued. No mercy.&#x20;

Sometimes, though, people design protocols that, on reflection, are just a dumb idea. Anyone remember early uncollateralized lending protocols? In that case, the only people harmed were investors. Unfortunately that idea made its way into some peer-to-peer lending protocols and users (lenders) _were_ harmed. Dumb doesn't eliminate liability.

### Implementation Bugs

No one writes bug-free software. We try in so many ways to limit or eliminate bugs, especially when human lives are involved, but we never  succeed. Rockets blow up and planes crash because of software bugs.&#x20;

DeFi protocols will never be bug-free. There is no way to  eliminate this type of protocol risk.&#x20;

## Clever Exploits

One of the great features of DeFi is "composability". This is the ability to mix-and-match smart contracts or even whole protocols. Composability is a standard software technique (e.g., functions, libraries) but it can be dangerous when developers have no control over the context in which their software will be used. Developers aren't clairvoyant so can't anticipate software that don't exist today, or software that behaves differently tomorrow.

Also, there's money involved, so the incentive to find weaknesses in multi-protocol combinations is very high. It happens all the time.

Recently, oracles and flash-loans have enable a lot of these exploits, but other weaknesses will be discovered and used. The details don't matter. What matters is that protocols, even well written, well audited protocols, can be exploited.  People who have funds in those protocols can lose them.&#x20;

Exploits in this class do not necessarily rely on bugs. Sometimes everything works as planned, but people still lose money.

## Mitigation Strategies

By now you've probably concluded that protocol risk is unavoidable, which is correct. People are clever, and money is a great motivator. If today's world doesn't make you anxious enough, spend some time reading the details of some of the biggest crypto exploits to date: [https://defiyield.app/rekt-database](https://defiyield.app/rekt-database).&#x20;

So how should companies and projects mitigate against protocol risk? Three ways:

1. Transparency
2. Insurance
3. Isolation

### Transparency

Bugs are inevitable, but, the more people look at designs and code, the more likely that bugs will be discovered before they cause harm. Software audits are common practice in DeFi. They help. An engaged community of developers can help even more.&#x20;

### Insurance

We know, it's old school, but it works.&#x20;

If you get sued because your protocol caused harm, your company or DAO could go out of business. Insurance can prevent a treasury from being drained by user lawsuits.

### Isolation

Most corporate structures isolate officers and shareholders from most liabilities. Similarly, a company can isolate a related company from liability.

Protocol risk can only be incurred by the entity developing and deploying the protocol. That entity does not need to be the same as the one controlling a company or project's treasury. Keeping those separate can limit the amount of financial damage caused by user lawsuits due to protocol failures.&#x20;

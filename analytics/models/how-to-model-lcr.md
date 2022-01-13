# How to model LCR?

LCR is defined as the proportion of highly liquid assets held by an organization to ensure that they maintain an ongoing ability to meet their short-term obligations (cash outflows for 30 days) in a stress situation. It is one of the essential liquidity risk measures in traditional finance. The mathematical formula is:

![](<../../.gitbook/assets/LCR calculation.png>)

**Liquidity buffer –** Highly liquid funds that that can be used to meet short-term obligations

**Net cash outflows -** net cash outflows from protocol users in a stress situation

****

**DATA NEEDED & CONSIDERATIONS:**&#x20;

To create an LCR model you will need two base-level data points:

1. Protocol Liquidity buffer: This variable will differ depending on the type of protocol you are modelling, as well the specific project you are investigating. To apply LCR effectively, ensure that the liquidity buffer you calculate consists of highly liquid assets- in other words something that could be used immediately to cover liabilities.
2. Total cash outflows for 30 days in a stressful scenario. As with the liquidity buffer, this will look different for different types of protocols. Modellers should consider normal cash outflows, and how they might be increased based on an adversarial environment.

It is important to remember that LCR is used to model; scenarios should be applied to understand how a protocol would perform under stress. Consider that these situations may impact both variables- for example by reducing the liquidity buffer and increasing total cash outflows.

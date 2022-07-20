# Balance Ratio

The balance ratio is an abstract measurement of how balanced value is among the tokens in a given liquidity pool. For a pool P, in this article we may write $$\textrm{br}(P)$$ to denote the balance ratio of P. The measure has the following useful features:

1. The balance ratio of a pool P satisfies $$\textrm{br}(P) = 1$$ if and only if the dollar value in the pool is evenly balanced among all tokens.
2. The balance ratio of pool P satisfies $$\textrm{br}(P) = 0$$​ if and only if the dollar value of at least one token in the pool is 0.
3. The balance ratio is "forgiving near the center", which means that if a pool is "fairly balanced" then its balance ratio will be very close to 1. For example, a two-token pool with value split 60:40 among the two tokens will have a balance ratio of 0.96.&#x20;

These features of the balance ratio offer the follow uses for measuring risk:

1. &#x20;A low balance ratio for a pool indicates that there is a heavy overweight of value in one token, which means more market participants are providing this token as liquidity to the pool. In the event that there is a run to sell the overweighted token, _the imbalance in the pool describes how many tokens will be unable to be swapped._
2. For stablecoins, this sell-pressure could be an indicator for potential [depegging](https://docs.credmark.com/dealing-with-risks/defi-and-crypto-specific-risks/depegging-risk). In cases where a stable coin has depegged, it can be telling to monitor the balance ratio as the token price moves (toward or away from its peg). For example, if the token regains its peg but the balance ratio continues to drop, this may indicate some underlying market dynamics have not yet recovered even though the price of the token has.

## For Two-Token Pools

### Definition

To define the balance ratio, we fix some notation for some of the quantities associated with a two-token liquidity pool.

* $$\textrm{tkn}_1$$, $$\textrm{tkn}_2$$ will be the names of the tokens
* $$p_1$$, $$p_2$$ will be the respective prices (in USD) of $$\textrm{tkn}_1$$ and $$\textrm{tkn}_2$$​
* $$n_1$$​, $$n_2$$​ will be the respective amounts of $$\textrm{tkn}_1$$​ and $$\textrm{tkn}_2$$ in the pool

​A first-order approximation of the value of $$\textrm{tkn}_1$$ (resp. $$\textrm{tkn}_2$$) in the pool is its market-cap: $$p_1 n_1$$ (resp. $$p_2n_2$$). Then an approximation of the total value in the pool is the sum of the market caps of $$\textrm{tkn}_1 \textrm{ and } \textrm{tkn}_2$$, $$p_1n_1+p_2n_2$$. Given these measures of value, the value ratio of $$\textrm{tkn}_1$$ is$$r_1 = \frac{p_1n_1}{p_1n_1 + p_2n_2}$$, and the value ratio of $$\textrm{tkn}_2$$​ is $$r_2 = \frac{p_2n_2}{p_1n_1 + p_2n_2}$$​.

The _balance ratio_ of a two-token pool P with values above $$\textrm{br}(P) = 4 r_1 r_2$$. Unwinding the definition, we can see that $$\textrm{br}(P) = 4\frac{(p_1n_1)(p_2n_2)}{(p_1n_1 + p_2n_2 )^2}$$​.

### Some examples

#### Abstract examples

The balance ratio is 1 exactly when the value of the pool is evenly split between both tokens.

The balance ratio is 0 exactly when one of the pool tokens represents all the value in the pool.&#x20;

The following table displays balance ratio values based on a few different value ratios.

| Value Ratio of Token 1 | Value Ratio of Token 2 | Balance Ratio   |
| ---------------------- | ---------------------- | --------------- |
| $$r_1$$​               | $$r_2$$                | $$\textrm{br}$$ |
| 0.5                    | 0.5                    | 1               |
| 0.6                    | 0.4                    | 0.96            |
| 0.7                    | 0.3                    | 0.84            |
| 0.8                    | 0.2                    | 0.64            |
| 0.9                    | 0.1                    | 0.36            |
| 0.99                   | 0.01                   | 0.0396          |
| 0.999                  | 0.001                  | 0.003996        |
| 1                      | 0                      | 0               |

#### FRAX-3CRV

As of July 1, 2022 the [FRAX-3CRV](https://curve.fi/frax) [pool](https://etherscan.io/address/0xd632f22692FaC7611d2AA1C0D552930D43CAEd3B) has approximately 761 million FRAX and 460 million 3CRV<mark style="color:red;">.</mark> Both are currently trading at close to $1, so we have $$r_{\textrm{FRAX}} \approx \frac{(1)(761 *10^6)}{(1)(761 *10^6) + (1)(460 *10^6)} = \frac{761}{1221} \approx 0.6232$$ and ​$$r_{\textrm{3CRV}} \approx \frac{(1)(460 *10^6)}{(1)(761 *10^6) + (1)(460 *10^6)} = \frac{460}{1221} \approx 0.3767$$​. The balance ratio of the pool is $$\textrm{br}(\textrm{FRAX-3CRV}) = 4 r_{\textrm{FRAX}} r_{\textrm{3CRV}} \approx 4 (0.6232)(0.3767) \approx 0.94$$.&#x20;

![](<../.gitbook/assets/Bildschirmfoto 2022-07-02 um 20.01.29.png>)

#### MIM-3CRV

As of July 1, 2022 the [MIM-3CRV](https://curve.fi/mim) [pool​](https://etherscan.io/address/0x5a6A4D54456819380173272A5E8E9B9904BdF41B) has approximately 73 million MIM and 7 million 3CRV. Both are currently trading at close to $1, so we have\
$$r_{\textrm{MIM}} \approx \frac{(1)(73 *10^6)}{(1)(73 *10^6) + (1)(7 *10^6)} = \frac{73}{80} \approx 0.9125$$ and\
$$r_{\textrm{3CRV}} \approx \frac{(1)(7 *10^6)}{(1)(73 *10^6) + (1)(7 *10^6)} = \frac{7}{80} \approx 0.0875$$. The balance ratio of the pool is ​$$\textrm{br}(\textrm{MIM-3CRV}) = 4 r_{\textrm{MIM}} r_{\textrm{3CRV}} \approx 4 (0.9125)(0.0875) \approx 0.32$$​.

![](<../.gitbook/assets/Bildschirmfoto 2022-07-02 um 19.59.38.png>)

### A metaphor from commercial real estate

Consider another abstract metric used in commercial real estate finance: the expense ratio. The expense ratio of a commercial real estate investment is $$\frac{\textrm{expenses}}{\textrm{revenue}}.$$ For skilled nursing facilities (SNFs), the average expense ratio is 0.82. If an investment opportunity with a 0.90 expense ratio landed on your desk, the higher-than-usual expense ratio _does not necessarily mean you toss it out​_, but it does suggest that you look more closely at the expenses as you evaluate the overall investment. Similarly, an expense ratio of 0.70 does not guarantee a good investment, but suggests that they may be doing something very efficient with their operations.

Another consideration would be that although expense ratios are normalized (take values between 0 and 1), it doesn't mean you should compare across categories. For example, multi-family homes have an average expense ratio of 0.4, but this "better number" doesn't mean every multi-family investment is better than every SNF investment. Context matters.

Similarly, the balance ratio offers a quick look at one feature of a liquidity pool. A ratio very close to 1 does not mean everything is okay with the tokens in that pool, but it _does indicate a fairly balanced liquidity pool._ Similarly, a balance ratio closer to 0.3 doesn't mean "RUN", but it does mean that if you're concerned about short-term liquidity, one token in this one pool may not be sufficiently liquid in the short-term. There may, for example, be other places that provide liquidity for the illiquid token, and the imbalance may be specific to this pool. Or not. Context matters.

For example, every constant-product AMM _defines the price of its tokens_ so that the balance ratio of its pools is always equal to 1. For these pools, the balance ratio being 1 _does not tell you very much about the tokens._ Context matters.

**Modeling Question:** what is the average balance ratio for two-token stablecoin pools on Curve?

**Modeling Question**: is there a strong correlation between volatility/depeg of a stablecoin TKN and the balance ratio of the corresponding TKN-3CRV pool?

## For Three-Token Pools

For a pool P with three tokens, $$\textrm{tkn}_1, \textrm{tkn}_2, \textrm{ and } \textrm{tkn}_3$$​, with corresponding prices $$p_1,p_2, \textrm{ and } p_3$$ and corresponding amounts in the pool $$n_1, n_2, \textrm{ and } n_3$$​ the corresponding value ratios are $$r_1 = \frac{p_1n_1}{p_1n_1+p_2n_2+p_3n_3}$$​, $$r_2 =  \frac{p_2n_2}{p_1n_1+p_2n_2+p_3n_3}$$​, $$r_3 = \frac{p_3n_3}{p_1n_1+p_2n_2+p_3n_3}$$. The balance ratio of the pool is defined to ​be $$\textrm{br}(P) = 27r_1r_2r_3 .$$​ Unwinding the definition gives $$\textrm{br}(P) = 27 \frac{p_1n_1p_2n_2p_3n_3}{(p_1n_1+p_2n_2+p_3n_3)^3}$$.​

| Value Ratio of Token 1         | Value Ratio of Token 2         | Value Ratio of Token 3        | Balance Ratio    |
| ------------------------------ | ------------------------------ | ----------------------------- | ---------------- |
| $$r_1$$​                       | $$r_2$$​                       | $$r_3$$​                      | $$\textrm{br}$$​ |
| $$\frac{1}{3} \approx 0.333$$​ | $$\frac{1}{3} \approx 0.333$$​ | $$\frac{1}{3} \approx 0.333$$ | 1                |
| 0.3                            | 0.3                            | 0.4                           | 0.972            |
| 0.2                            | 0.4                            | 0.4                           | 0.864            |
| 0.2                            | 0.3                            | 0.5                           | 0.81             |
| 0.2                            | 0.2                            | 0.6                           | 0.648            |
| 0.1                            | 0.3                            | 0.6                           | 0.486            |
| 0.1                            | 0.2                            | 0.7                           | 0.378            |
| 0.1                            | 0.1                            | 0.8                           | 0.216            |
| 0                              | 0.5                            | 0.5                           | 0                |

**Modeling Question:** What is the average balance ratio for three-token pools on Curve?

## The general picture

In general, suppose we have a pool P with $$n$$​ tokens with the i-th tokens price and amount and value ratio given by $$p_i, n_i, \textrm{ and } r_i = \frac{p_i n_i}{\sum_{k=1}^n p_k n_k}$$​. Then the balance ratio is given by $$\textrm{br}(P) = n^n  r_1 r_2 \cdots r_n = \frac{\prod_{k=1}^n p_k n_k}{(\sum_{k=1}^n p_k n_k)^n}$$.&#x20;

### Geometry of the balance ratio

The balance ratio can be described using the geometry of n-dimensional cubes. Note that as value moves between tokens in the pool (whether by swaps or liquidity changes), the relative sizes of $$r_1, r_2, \ldots, r_n$$ change​, but their sum remains constant $$\sum_{k=1}^nr_k = 1.$$ Interpreting the numbers $$r_1, r_2, \ldots, r_n$$ as the length, width, height, 4-dimensional length, 5-dimensional length, ​..., $$n$$-dimensional length of an n-dimensional rectangle means that the product $$\prod_{k=1}^n r_k$$​ can be interpreted as the n-dimensional volume.&#x20;

Among all such $$n$$​-dimensional rectangles where the sum of the lengths is constant (1 in our case), the rectangle with the _highest volume_ is the $$n$$​-dimensional cube. The balance ratio will be the volume of the $$n$$​-dimensional rectangle defined by our pool divided by the volume of the $$n$$​-dimensional cube whose lengths add to 1.

By definition, the cube has all of its lengths the same size; since they add to 1, and there are $$n$$​ of them, each of the cube's lengths is equal to $$\frac{1}{n}$$​, so the volume of this cube is $$\prod_{k=1}^n \frac{1}{n} = (\frac{1}{n})^n.$$ This gives $$\textrm{br}(P) = \frac{r_1 r_2 \cdots r_n}{(\frac{1}{n})^n} = n^n r_1 r_2 \cdots r_n$$​ as above. When $$n = 2$$​ we recover the first formula for two-token pools $$\textrm{br}(P)=4 r_1 r_2$$​ and when $$n=3$$​ we recover the formula for three-token pools $$\textrm{br}(P)=27 r_1 r_2 r_3$$​.

## Contributors

| Discord Handle  | ETH Address | Reward            | Contribution     |
| --------------- | ----------- | ----------------- | ---------------- |
| corepresentable |             | 0 $CMK (internal) | Original version |


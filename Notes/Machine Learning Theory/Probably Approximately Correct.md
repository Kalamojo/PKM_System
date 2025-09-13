---
aliases:
  - PAC
subject: Machine Learning Theory
tags:
  - masters
---
# Probably Approximately Correct

>[!note]
> A [[Function|Hypothesis]] that is "probably" (with [[Probability]] $1-\delta$), "approximately" (up to an error of $\epsilon$) correct for a given [[Distribution]] of [[Feature|features]].

> [!math]
> $$\text{err}_{\mathcal{D},f}(h) \leq \mathcal{E}$$
> with probability $1 - \delta$
> - $\mathcal{D}=$ unknown [[Distribution]]
> - $f=$ unknown [[Ground Truth]] labeling [[Function]]
> - $\delta=$ [[Delta Function]], or probability of failure
> - $\mathcal{E}=$ allowed accuracy slack, or the amount of [[Error Term|Error]] allowed

## References
1. [[Function|Hypothesis]]
2. [[Probability]]
3. [[Error Term]]
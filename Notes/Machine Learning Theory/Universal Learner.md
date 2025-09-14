---
aliases: []
subject: Machine Learning Theory
tags:
  - masters
---
# Universal Learner

>[!note]
> An [[Algorithm]] that can learn *any* target [[Function]] $f$ under *any* [[Distribution]] $\mathcal{D}$. There are no assumptions on the [[Hypothesis Class]].

> [!math]
> For every
> $$0 \lt \mathcal{E},\delta \lt 1,$$
> for **every*** [[Distribution]] $\mathcal{D}$, and for ***every*** [[Label|labeling]] [[Function]] $f$, 
> 
> given enough samples, with [[Probability]] at least $1 - \delta$, the learner should output a [[Function|Hypothesis]] $h$ with [[Error Term|Error]]
> $$\text{err}_{\mathcal{D},f}(h) \leq \mathcal{E}$$

## References
1. [[Algorithm]]
2. [[Ground Truth]]
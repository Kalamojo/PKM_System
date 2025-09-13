---
aliases:
  - PAC-learnable
subject: Machine Learning Theory
tags:
  - masters
---
# PAC Learnability

>[!note]
> A [[Hypothesis Class]] $\mathcal{H}$ is PAC-learnable if there exists an [[Algorithm]] $A$ with a complexity function $m_\mathcal{H}$, such that the algorithm will return a [[Probably Approximately Correct]] [[Function|Hypothesis]] $h$.

> [!math]
> For all
> $$0 \lt \mathcal{E},\delta \lt 1,$$
> all possible [[Distribution|distributions]] $\mathcal{D}$ over all [[Feature|Inputs]] $\mathcal{X}$, and all [[Label|labeling]] [[Function|functions]] $f$, if the [[Realizability Assumption]] holds with respect to $\mathcal{H}$, $\mathcal{D}$, $f$, 
> 
> then when given
> $$m \geq m_\mathcal{H}(\mathcal{E},\delta)$$
> samples, with probability at least $1 - \delta$, $A$ returns $h$ with [[Error Term|Error]]
>  $$\text{err}_{\mathcal{D},f}(h) \leq \mathcal{E}$$
>  - $m_\mathcal{H}=$ the [[Sample Complexity]] of learning $\mathcal{H}$
> 
> If such an algorithm $A$ exists, then $\mathcal{H}$ is PAC-learnable.

## References
1. [[Probably Approximately Correct]]
2. [[Algorithm]]
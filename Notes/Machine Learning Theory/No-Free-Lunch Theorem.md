---
aliases: []
subject: Machine Learning Theory
tags:
  - masters
---
# No-Free-Lunch Theorem

>[!note]
> Shows that a [[Universal Learner]] does not exist.

> [!math]
> Given any [[Learning]] [[Algorithm]] $A$ for [[Binary Classification]] over an [[Domain|Input Space]] $\mathcal{X}$, and $m$ (sample size) as any number smaller than $|\mathcal{X}|/2$ to represent the [[Training Set]] size.
> 
> Then [[Existential Quantifier|there exists]] a [[Distribution]] $\mathcal{D}$ and a [[Label|labeling]] [[Function]] $f$ such that:
> 
> With [[Probability]] at least $1/7$ over [[Training Set]] $S$, the returned classifier $A(S)$ has true [[Error Term|Error]]
> $$\text{err}_{\mathcal{D},f}(A(S)) \geq 1/8$$

> [!info]
> The implication is that no single [[Algorithm]] will work well on *all* distributions, so prior knowledge (restricting [[Hypothesis Class]] $\mathcal{H}$) is necessary for learnability.

## References
1. [[Universal Learner]]
2. [[Algorithm]]
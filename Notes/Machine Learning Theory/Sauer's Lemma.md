---
aliases:
  - Sauer-Shelah Lemma
subject: Machine Learning Theory
tags:
  - masters
---
# Sauer's Lemma

>[!note]
> Establishes the [[VC Dimension]] as a measure of true capacity/complexity of a [[Hypothesis Class]] $\mathcal{H}$. It basically states that every Hypothesis Class with small [[VC Dimension]] contains a small number of different [[Function|functions]] as well.

> [!math]
> if $\text{VCDim}(\mathcal{H})=d$, then:
> $$\Pi_\mathcal{H}(m) \leq \sum_{i=0}^{d} {m \choose i}$$

## References
1. [[VC Dimension]]
2. [[Growth Function]]
---
aliases: []
subject: Machine Learning Theory
tags:
  - masters
---
# Growth Function

>[!note]
> For a [[Training Set]] $S$ of size $m$, and [[Hypothesis Class]] $\mathcal{H}$, this is the maximum number of ways points in $S$ can be [[Label|labelled]] using hypotheses in $\mathcal{H}$.

> [!math]
> For a set of unlabeled [[Feature|Inputs]]
> $$S=\{x_1,\dots,x_m\},$$
> define $\mathcal{H}[S]$ as the set of all different ways to [[Label]] points in $S$ using [[Function|hypotheses]] in $\mathcal{H}$:
> $$\mathcal{H}[S]=\{(h(x_1),\dots,h(x_m)): h \in \mathcal{H}\}$$
> The Growth Function thereby is defined as:
> $$\Pi_\mathcal{H}(m)=\underset{S\in\mathcal{X}^m}{\text{max}}|\mathcal{H}[S]|$$
> or in other words, the maximum [[Cardinality]] of $\mathcal{H}[S]$.

> [!info]
> $\Pi_\mathcal{H}(m)$ has a ceiling of $2^m$, since there are only $2^m$ possible ways of [[Label|labeling]] points in [[Binary Classification]].

## References
1. [[Training Set]]
2. [[Cardinality]]
3. [[Hypothesis Class]]
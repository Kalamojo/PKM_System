---
aliases: []
subject: Machine Learning Theory
tags:
  - masters
---
# Consistent Hypothesis

>[!note]
> A [[Function]] from the [[Hypothesis Class]] that labels all observed inputs perfectly, without error.

> [!math]
> Represented by:
> $$h^\star,$$
> given a [[Training Set]] $S$, $h$ is consistent with $S$ if:
> $$h(x_i)=y_i$$
> for all $i$.
> - $x_i=$ the $i^{ith}$ [[Feature]]
> - $y_i=$ the $i^{ith}$ true [[Label]]

> [!info]
> There is a key [[Difference]] between a Consistent Hypothesis and [[Ground Truth]]:
> 
> Consistent Hypotheses achieve 0 [[Error Term|error]] on finite, *observed* [[Data]] from the Training Set. However, this does not guarantee 0 error on unseen data.

## References
1. [[Function]]
2. [[Hypothesis Class]]
3. [[Training Set]]
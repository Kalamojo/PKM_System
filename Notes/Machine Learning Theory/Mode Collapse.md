---
alias: []
subject: Machine Learning Theory
tags:
  - masters
---
# Mode Collapse

>[!note]
> Where a model's outputs become less diverse and repetitive, converging to only a narrow subset of possible answers.

>[!math]
> Mode Collapse rate:
> $$\frac{|\{y \in Y(x): y \notin f(x)\}|}{|Y(x)|}$$
> In other words:
> > [!info]
> > Given a [[Function]] $f(x)$, this is the size of [[Ground Truth]] $Y(x)$ outputs $y$ that are not produced by the function, divided by the size of Ground Truth given all inputs $x$.

> [!example]
> Human\> Tell me some facts about Vincent van Gogh.
> Model\>
> - Painted Starry Night ✅
>
> While correct, the model misses some true facts.

## References
1. [[Modern ML]]
2. [[Ground Truth]]
3. [[Feature]]
4. [[Label]]
5. [[Function]]
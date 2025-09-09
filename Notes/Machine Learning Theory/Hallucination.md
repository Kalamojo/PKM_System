---
alias: []
subject: Machine Learning Theory
tags:
  - masters
---
# Hallucination

>[!note]
> When models generate information that sounds plausible, yet is factually incorrect or completely fabricated.

>[!math]
> Hallucination Rate:
> $$\frac{| \{y \in f(x): y \notin Y(x)\} |}{|f(x)|}$$
> In other words: 
> >[!info]
> > Given a [[Function]] $f(x)$, this is the size of outputs $y$ that are not [[Ground Truth]] $Y(x)$ (that are incorrect), divided by the size of all outputs by the function for all inputs $x$.

> [!example]
> Human\> Tell me some facts about Vincent van Gogh.
> Model\>
> - Painted Starry Night ✅
> - Lived in the Netherlands ✅
> - Cut off part of his ear ✅
> - Invented Cubism ❌
> - Was born in Italy ❌
>
> The model outputs some false facts.

## References
1. [[Modern ML]]
2. [[Function]]
3. [[Feature]]
4. [[Label]]
5. [[Ground Truth]]
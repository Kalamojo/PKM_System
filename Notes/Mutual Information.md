---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# Mutual Information

> [!note]
> A measurement of how much information is being communicated between one variable and another. In other words, how much does variable $Y$ depend on variable $X$?

> [!math]
> Formally, it is equal to the Shannon entropy of variable $X$ + Shannon entropy of variable $Y$ - the joint entropy of $X$ and $Y$:
> 
> $I(X, Y) = H(X) + H(Y) - H(X,Y)$
> $I(X ; Y)=\sum_{x \in \mathcal{X}} \sum_{y \in \mathcal{Y}} p(x, y) \log \frac{p(x, y)}{p(x) p(y)}$

## References
1. [[Shannon Entropy]]
2. [[Joint Entropy]]
3. [[Association]]
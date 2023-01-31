---
alias: [Expected surprise]
subject: Data Science Intro
tags: [school]
---
# Entropy

> [!note]
> The expected surprise of an event. Is a sum of all probabilities multiplied by their respective surprise.

> [!example] 
> Entropy of flipping a weighted coin:
> - 90% of the time, it is heads.
> - 10% of the time, it is tails.
> $(0.9 * \log_2(1/0.19)) + (0.1 * \log_2(1/0.1)) = 0.467$
> 
> $$\text{Entropy} = \sum \log_2(\frac{1}{p(x)})*p(x)$$
> $p(x) = \text{probability}$

## References
1. [[Surprise]]
2. [[Probability]]
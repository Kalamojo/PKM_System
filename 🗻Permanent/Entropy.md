---
alias: [Expected surprise, Randomness, Uncertainty]
subject: Data Science Intro
tags: [school]
---
# Entropy

> [!note]
> Also known as randomness or uncertainty. It is the expected surprise of an event, and can be calculated as the sum of all probabilities multiplied by their respective surprise.

> [!example] 
> Entropy of flipping a weighted coin:
> - 90% of the time, it is heads.
> - 10% of the time, it is tails.
> 
> $(0.9 * \log_2(1/0.9)) + (0.1 * \log_2(1/0.1)) = 0.469$

> [!math]
> $$\text{Entropy} = \sum \log_2(\frac{1}{p(x)})*p(x)$$
> - $p(x) = \text{probability}$

## References
1. [[Surprise]]
2. [[Probability]]
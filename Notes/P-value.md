---
aliases: []
subject: Data Science Intro
tags:
  - undergrad
---
# P-value

> [!note]
> The probability that an event happens in the world. The lower the p-value, the more surprising the edivence is. When a p-value is low enough (usually a threshold of 5%), then a hypothesis can be rejected.

> [!math]
> P-value = 1 divided by number of all possibilities + probability of observing something equally rare as observation + probability of more-rare observation

> [!example]
> When flipping a coin twice, what is the probability of getting 2 heads?
> - Probability of 2 heads out of all possibilities?: 1/4 (HH, HT, TH, TT)
> - Probability of getting 2 tails?: 1/4 (equally as rare as 2 heads)
> - Probability of getting a rarer combination?: 0 (TH is equal to HT, so is less rare)
> 
> P-value = 0.25 + 0.25 + 0 = 0.5
> Coin is not abnormal or weighted (null hypothesis was not rejected) since p-value was greater than 0.5.

## References
1. [[Hypothesis Test]]
2. [[Probability]]
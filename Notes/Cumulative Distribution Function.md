---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# Cumulative Distribution Function

> [!note]
> A function that gives the probability that a discrete random variable is at most equal to some value (less than or equal to a value).

> [!math]
> $$F(x) = P(X \le x) \quad \text{for all } -\infty < x < \infty$$
> When $X$ is discrete, $F$ is given as
> $$F(x) = P(X \le x) = \sum_{u \le x} f(u)$$
> When $X$ is continous, $F$ is given as
> $$F(x) = P(X \le x) = \int_{-\infty}^x f(u) \,du$$

```ad-example
Cumulative density function for rolling a 3:
$$F(3) = P(X \leq 3) = \frac{1}{6} * 3 = \frac{1}{2}$$
```

## References
1. [[Probability]]
2. [[Probability Mass Function]]
3. [[Probability Density Function]]
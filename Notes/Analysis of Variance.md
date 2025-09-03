---
alias: [ANOVA]
subject: Data Science Intro
tags: [undergrad]
---
# Analysis of Variance

> [!note]
> A single statistic that allows comparison of variance between groups with variance within groups.

> [!math]
> $F = \frac{VAR_{between}}{VAR_{within}}$
> 
> $VAR_{between}$ degrees of freedom $= m - 1$
> $VAR_{within}$ degrees of freedom  $= m * (n - 1)$
> $m=$ number of groups
> $n =$ size of groups

> [!note]
> The higher the F-value is, the less probable is the null hypothesis that the groups came from the same population.

## References
1. [[F-Statistic]]
2. [[Sample Variance]]
3. [[Hypothesis Test]]
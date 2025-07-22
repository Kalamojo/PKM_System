---
alias: [r^2, Coefficient of Determination]
subject: Data Science Intro
tags: [school]
---
# R-Squared

```ad-note
A measure of how well a Linear Regression Model performs. It is calculated using the performance on the mean of the testing values as well as the standard fit of the testing values.
The Higher the $R^2$, the better
```

```ad-math
Variation around mean $= \frac{(data-mean)^2}{n} = \frac{SS(mean)}{n}$
- $SS=$ Residual Sum of Squares

Variation around fit $= \frac{(data - prediction)^2}{n} = \frac{SS(fit)}{n}$

$$R^2 = \frac{Var(mean) - Var(fit)}{Var(mean)}$$
```

```ad-warning
Is not very reliable with few datapoints. For example, a model fitted on a dataset wtih only 1 feature and 2 points will have an $R^2$ of 1, implying that it is perfect.
```

## References
1. [[Notes/Linear Regression]]
3. [[Variance]]
4. [[Residual Sum of Squares]]
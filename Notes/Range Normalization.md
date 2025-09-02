---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# Range Normalization

```ad-note
Looking at datapoints $x_1, x_2,....,x_n$, range normalization will scale each value by the range of the datapoints.
```

```ad-math
$$x_{i}^{\prime}=\frac{x_{i}-\min _{i}\left\{x_{i}\right\}}{\hat{r}}=\frac{x_{i}-\min _{i}\left\{x_{i}\right\}}{\max _{i}\left\{x_{i}\right\}-\min _{i}\left\{x_{i}\right\}}$$
$\hat{r} = \text{range of datapoints}$
```

## References
1. [[Normalization]]
2. [[Range]]
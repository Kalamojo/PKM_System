---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# BIC for K-means

```ad-note
Since there is no maximum likelihood for a K-means clustering model, the distance between every item and its centroid is used instead. This method also penalizes for model complexity (number of clusters and datapoints).

```

```ad-math
$${BIC}_{RSS} = RSS + \ln{(M)}B$$

$\mathrm{RSS}=\sum_{k=1}^{K} \sum_{x \in C_{k}}\left|x-\mu^{k}\right|^{2}$
$B = (\text{\# clusters}) * (\text{\# dimensions})$
$M=$ number of datapoints
```

## References
1. [[Bayesian Information Criterion]]
2. [[Centroid]]
3. [[Residual Sum of Squares]]
---
alias: [BIC]
subject: Data Science Intro
tags: [undergrad]
---
# Bayesian Information Criterion



```ad-note
BIC determies how well a model fits the data it was trained on in a probabilistic sense. The measure is balanced by the number of parameters being analyzed.
It is computationally more efficient than the AIC evaluation.
```

```ad-math
$$BIC = -2 \ln{L} + B \ln{(M)}$$
$L=$ maximum likelihood of the model
$B=$ number of free parameters (features) being analyzed
$M=$ number of datapoints
```

```ad-info
BIC can respond to more and more datapoints, increasing the penalty.
```

## References
1. [[Maximum Likelihood Estimation]]
2. [[Aikaike Information Criterion]]
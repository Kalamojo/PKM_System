---
aliases: []
subject: Data Science Intro
tags:
  - undergrad
---
# Ordinary Least Squares

> [!note]
> For each feature of a model (and every datapoint of a feature), OLS calculates the sum of the difference between the actual dependent $y$ and the predicted $y$.

> [!math]
> $\text { total error }=\sum_{i}\left(y_{i}-\widehat{y}_{i}\right)^{2}=\sum_{i}\left(y_{i}-\sum_{k} w_{k} x_{k}^{(i)}\right)^{2}$

## References
1. [[Notes/Loss Function]]
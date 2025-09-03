---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# AIC for K-means

> [!note]
> Since there is no maximum likelihood for a K-means clustering model (there are no calculated weights to be multiplied by values), the distance between every item and its centroid is used instead.
> 

> [!math]
> ${AIC}_{RSS} = RSS + B$
> 
> $\mathrm{RSS}=\sum_{k=1}^{K} \sum_{x \in C_{k}}\left|x-\mu^{k}\right|^{2}$
> $B = (\text{\# clusters}) * (\text{\# dimensions})$

## References
1. [[Aikaike Information Criterion]]
2. [[Centroid]]
3. [[Residual Sum of Squares]]
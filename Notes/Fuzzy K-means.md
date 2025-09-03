---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# Fuzzy K-means


> [!note]
> A clustering algorithm that calculates the responsibility/proportion of a class in every datapoint, as opposed to determining one absolute class.

> [!math]
> The responsibility of centroid $i$ for a datapoint $j$ is proportional to:
> 
> ${Force}_{i,j} = e^{-\beta * distance(Data j, Center i)}$
> Where $\beta$ is a stiffness parameter.

## References
1. [[Soft Clustering]]
2. [[K-Means Clustering]]
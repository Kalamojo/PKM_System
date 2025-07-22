---
alias: []
subject: Data Science Intro
tags: [school]
---
# K-Means Clustering

```ad-note
Involves pre-selecting a number of clusters and then partitioning points into the different clusters based on similarity.
```

```ad-info
1. Centroids are placed in random areas (though pre-selecting can produce better results).
2. Repeat these steps until no changes occur:
	1. Centroids are positioned to the center (average) of their assigned points
	2. Points closest to a given centroid are assigned to that centroid
```

```ad-example
![A complete guide to K-means clustering algorithm - KDnuggets|center](https://cdn-images-1.medium.com/max/1600/0*GePJBQORYP8sLKRE)
```

```ad-math
Objective:
$$\min _{\mu} \min _{C} \sum_{i=1}^{k} \sum_{x \in C_{i}}\left|x-\mu_{i}\right|^{2}$$
> 1. Fix $\mu$, optimise $C$:
>    $$\min _{C} \sum_{i=1}^{k} \sum_{x \in C_{i}}\left|x-\mu_{i}\right|^{2}=\min _{c} \sum_{i}^{n}\left|x_{i}-\mu_{x_{i}}\right|^{2}$$
> 2. Fix $C$, optimise $\mu$:
>    $$\min _{\mu} \sum_{i=1}^{k} \sum_{x \in C_{i}}\left|x-\mu_{i}\right|^{2}$$
```

## References
1. [[Notes/Clustering]]
2. [[Centroid]]
3. [[Sample Mean]]
4. [[Euclidian Distance]]
5. [[K-means Clustering Terminology]]
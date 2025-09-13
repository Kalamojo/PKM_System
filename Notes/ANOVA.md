---
aliases:
  - Analysis of Variance
tags:
  - personal
---
# ANalysis Of VAriance (ANOVA)


> [!info] 
> There is a fundamental idea behind ANOVA that can give us some information about the means of various samples. 

> [!example]
> Consider this table of 3 different populations of the hours employees work in various deparments:
> 
> | Departments   |     Hours      |
> | ------------- |:--------------:|
> | Department A: | 35, 36, 37, 38 |
> | Department B: | 45, 46, 47, 48 |
> | Department C: | 55, 56, 57, 58 |
> 
> The [[Variance]] between the different departments is fairly high, but the the variance within each department is low. In this case, because the different departments are varied much more than the samples within each one, we can ssume that their means are different.
> 
> Here is a different example in the same setting:
> 
> | Departments   |     Hours      |
> | ------------- |:--------------:|
> | Department A: | 30, 40, 50, 60 |
> | Department B: | 31, 41, 51, 61 |
> | Department C: | 32, 42, 52, 62 |
> 
> In this example, the variance between departments is low, while the variance within them is considerably high. Contrary to the previous example, because the variances within each department are much higher than between them, we can assume that the means are fairly close to one another.

> [!math]
> Sum of squares between = 
>  $\sum_{i = 1}^{k} n_i(\overline{X_i} - \overline{X})^2$
> with $n_i$ being the number of samples and $\overline{X_i}$ being the mean of one population and $\overline{X}$ being the total mean
> 
> Sum of squares within =
> $\sum_{i = 1}^{k} (n_i-1)s_i^2$
> with $s_i$ being the [[Variance]]

> [!seealso]
> ### Anova Table
> | Source of variation         | Degrees of freedom | Sum of squares | Mean Square             | F statistic    |
> | --------------------------- | ------------------ | -------------- | ----------------------- | -------------- |
> | Treatments (Between Groups) | $k - 1$             | $SS_{between}$      | $MS_{between} = \frac{SS_{between}}{k - 1}$ | $F = \frac{MS_{between}}{MS_{error}}$ |
> | Error (Within groups)       | $N - k$            | $SS_{error}$        | $MS_{error} = \frac{SS_{error}}{N - k}$     |                |
> | Total                       | $N - 1$            | $SS_{total}$        |                         |                | 
> 
> - K: number of populations
> - N: total number of sample measurements
> - $MS_{between}$: Variation between the groups
> - $MS_{error}$: Variation within the groups

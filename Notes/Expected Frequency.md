---
aliases: []
subject: Data Science Intro
tags:
  - undergrad
---
# Expected Frequency


The expected frequency of a count is calculated using proability and proportions compared to the total values in the table.

> $$E_{ij} = \frac{T_i * T_j}{N}$$
> $E_{ij} =$ expected frequency for the *i*th row/*j*th column
> $T_i=$ total in the ith row
> $T_j=$ total in the jth column
> $N=$ table grand total

Example:

|              | Voted          | Didn't Vote | Total |
| ------------ | -------------- | ----------- | ----- |
| Experimental | ==65== (E = ?)     | 49          | 114   |
| Control      | 37             | 22          | 59    |
| Total        | 102            | 71          | 173   |

|              | Voted               | Didn't Vote | Total   |
| ------------ | ------------------- | ----------- | ------- |
| Experimental | ==E = (114 * 102)/173== | 49          | ==114==     |
| Control      | 37                  | 22          | 59      |
| Total        | ==102==                 | 71          | ==173==     |

$E_{1, 1} = 67.214$

## References
1. [[Probability]]
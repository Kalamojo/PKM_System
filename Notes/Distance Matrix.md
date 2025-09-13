---
aliases: []
subject: Data Science Intro
tags:
  - undergrad
---
# Distance Matrix


> [!note]
> Given multiple datapoints for one attribute, displays the Euclidian Distance between each datapoint.

> [!example]
> ```chart
> type: line
> labels: [0, 1, 2, 3, 4, 5, 6]
> series:
>   - title: p1
>     data: [2,-,-,-,-,-,-]
>   - title: p2
>     data: [-,-,0,-,-,-,-]
>   - title: p3
>     data: [-,-,-,1,-,-,-]
>   - title: p4
>     data: [-,-,-,-,-,1,-]
> width: 80%
> beginAtZero: true
> ```
> 
> |     | p1    | p2    | p3    | p4    |
> | --- | ----- | ----- | ----- | ----- |
> | p1  | 0     | 2.828 | 3.162 | 5.099 |
> | p2  | 2.828 | 0     | 1.414 | 3.162 |
> | p3  | 3.162 | 1.414 | 0     | 2     |
> | p4  | 5.099 | 3.162 | 2     | 0     |

## References
1. [[Euclidian Distance]]
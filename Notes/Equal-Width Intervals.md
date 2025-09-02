---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# Equal-Width Intervals

> [!note]
> Partition the range of values ($X$) into $k$ equal-width intervals.

> [!math] 
> $$w = \frac{x_{max} - x_{min}}{k}$$
> $w=\text{width of intervals}$
> $k=\text{number of intervals}$
> 
> The upper-boundary of the $i_{th}$ interval is given as:
> $v_i = x_{min} + i*w$, for $i=1,....,k-1$

> [!example]
> ![[Pasted image 20220301201340.png]]

## References
1. [[Discretization]]
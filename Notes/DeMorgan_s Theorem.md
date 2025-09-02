---
alias: []
subject: Digital Systems Engineering
tags: [undergrad]
---
# DeMorgan's Theorem

```ad-note
$(x * y)' = x' + y'$ | $(x + y)' = x' * y'$
```

```ad-info
Proof:

| $x$ | $y$ | $x * y$ | $\overline{x * y}$ | $\bar{x}$ | $\bar{y}$ | $\bar{x} + \bar{y}$ |
| - | -- | ----- | ---- | -- | - | ----- |
| 0 | 0  | 0     | 1    | 1  | 1 | 1     |
| 0 | 1  | 0     | 1    | 1  | 0 | 1     |
| 1 | 0  | 0     | 1    | 0  | 1 | 1     |
| 1 | 1  | 1     | 0    | 0  | 0 | 0     |
```

## References
1. [[OR]]
2. [[AND]]
3. [[Binary Variable]]
4. [[Theorem]]
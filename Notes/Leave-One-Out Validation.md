---
alias: [LOOCV, Leave-One-Out Cross Validation, Leave-One-Out Cross-Validation]
subject: Data Science Intro
tags: [school]
---
# Leave-One-Out Validation

```ad-note
Similar to K-Fold Validation, except instead of dividing data into equal portions, data is separated into 2 groups: 1 data, and the rest of the data.
The model is trained with the rest of the data, tested on the remaining 1 data, and repeats this process untill all data has been analyzed.
```

```ad-info
Because it trains so many times, it is useful for machine learning on snmall datasets.
```

## References
1. [[K-Fold Cross Validation]]
2. [[Notes/Supervised Learning]]
3. [[Notes/Training]]
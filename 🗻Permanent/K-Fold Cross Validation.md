---
alias: [K-Fold Cross-Validation]
subject: Data Science Intro
tags: [school]
---
# K-Fold Cross Validation


```ad-note
A technique used to evaluate a machine learning model's performance on a dataset divided into K subsets.
```

```ad-example
- First, a dataset is divided into 5 sets. The machine learning model is trained on set 1, set 2, set 3, and set 4. Then, it tests itself on set 5. The result of this test is then used to evaluate the model's overall performance.
- The model is then trained on set 1, 2, 3, and 5. Then, it is tested on set 4. The result of the test is included in the model's overall performance.
	- This process is repeated untill all subsets have been tested for.
- The either the sum or average of all 5 tests are used to tally a final evaluation for the accuracy of the model.
```

## References
1. [[🗻Permanent/Supervised Learning]]
2. [[🗻Permanent/Training]]
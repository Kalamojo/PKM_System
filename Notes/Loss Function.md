---
aliases:
  - Cost Function
tags:
  - personal
---
## Loss Function

> [!note]
> The average loss of all datapoints in a training dataset. Determines how good a given function from the [[Hypothesis Class]] is.

> [!info]
> The Error/Loss Function gives a measure of how poor a prediction is. When a large error is detected, model weights are substantially reduced. When a correct prediction is made with little error, weights are reinforced.

#⌛TBC Separate into different notes
## 0/1 Loss
> [!math]
>$\ell_{0/1}(h_i D) =$ $$\frac{1}{n}\sum_{(x_i, y_i) <- D}\delta[h(x_i) \neq y_i]$$
>$h=$ function from the [[Hypothesis Class]]
>$D=$ [[Data]] set
>$x=$ independent variable
>$y=$ dependend variable
>$\delta=$ the [[Delta Function]]

This basically counts how many times the function is wrong when evaluaing your dataset, and expresses it as a percentage.

## Square Loss
> [!math]
>$\ell_{sq}(h_i D) =$ $$\frac{1}{n}\sum_{(x_i, y_i) <- D}(h(x_i) - y_i)^2$$

Used in [[Regression]] problems

## Absolute Loss
> [!math]
>$\ell_{ab}(h_i D) =$ $$\frac{1}{n}\sum_{(x_i, y_i) <- D}|h(x_i) - y_i|$$

Unlike the square loss, extreme outliers don't have quite as much weight on the overall [[Error Term|error]].

## References
1. [[Hypothesis Class]]
2. [[Weight]]
3. [[Error Term]]
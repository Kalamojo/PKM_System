---
alias: []
subject: Data Science Intro
tags: [undergrad]
---
# Linear Regression

```ad-note
Assuming that some output data is generated using some input features (due to some unknown function), Linear Regression tries to find an identical function (plus some error).
```

```ad-math
$$y=f(x) + \epsilon$$
$y =$ true data
$f(x) =$ generated machine learning function
$\epsilon =$ error
```

```ad-info
Can be as simple as some weight multiplied by an input feature + some bias. It finds the correct weight and bias by trying out some value, calculating the error, and adjusting accordingly. This is accomplished by calculating the [[Error Term]] of the best fit line and thereby seeing how "good" its initial guesses are. Stops when the error is minimized.
```

> [!example] 
> ![[Drawing 2021-11-16 18.26.32.excalidraw]]
>The graph of this equation is $y = b_0 + b_1* x$

## References
1. [[Regression]]
2. [[Notes/Supervised Learning]]
3. [[Notes/Weights]]
4. [[Bias]]
5. [[Ordinary Least Squares]]
6. [[Residual Sum of Squares]]
7. [[Batch Gradient Descent|Gradient Descent]]
8. [[Algorithm]]
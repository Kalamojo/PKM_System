---
alias: [Gradient Descent]
tags: [personal]
---
# Batch Gradient Descent

> [!note]
> Gradient Descent is an Algorithm that minimizes the cost function. It essentially finds which model paramenters bring error to the lowest value possible.
> Batch Gradient Descent, as opposed to other similar algorithms, uses all training examples during each step.

> [!info] 
> Process repeated until convergence:
> 1. Start with some initial paramenter guesses
> 2. Change parameters to lower error locally

> [!math]
> $$\theta_{j} := \theta_{j} - \alpha \cdot \frac{\partial}{\partial \theta_{j}} \cdot J([\theta_{0}, \theta_{1}, ..., \theta_{n}])$$
> $\theta_{j} =$ given parameter
> $\alpha =$ learning rate, or how large of a step should be taken
> $J(...) =$ cost function of model with all parameters

````ad-example
```python
import numpy as np
import matplotlib.pyplot as plt


x = np.linspace(-5,5,100)

def f(x):
    return 3*x**6+4*x**5+x**4+x**3-3*x**2+x

y = f(x)

plt.plot(x, y, '-r', label='y=2x+1')
plt.axis([-4, 4, -9, 9])
plt.scatter(1, f(1))

plt.show()


alpha = 0.05
theta = 1

def d_fun(x):
    h = 1e-5 #in theory h is an infinitesimal
    return (f(x+h)-f(x))/h

  

def grad(theta):
    athena = theta - alpha * d_fun(theta)
    if abs(athena - theta) < 0.01:
        return athena
    else:
        return grad(athena)
  
print(grad(theta))
````

## References
1. [[Notes/Loss Function|Cost Function]]
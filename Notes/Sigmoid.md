---
aliases: []
tags:
  - personal
---
# Sigmoid

> [!note]
> Sigmoid [[Neurons]] are very similar to [[Perceptron|Perceptrons]], but wheres perceptrons take [[Binary]] inputs and produce binary outputs, Sigmoid neurons are a lot more nuanced.
> Sigmoid neuron inputs can be 0, 1, and anything in between. Likewise, the outputs are not simply 0s or 1s. 

> [!math]
> ## Basic Equation
> The exact equation for calculating the output is this:
> $$\sigma(w⋅x+b)$$
> with $w$ representing the [[Weight]] of the input, $x$ representing its value, $b$ representing the [[Bias]], and $\sigma$ representing a new variable: the [[Sigmoid Function]].

> [!math]
> ## Expanded Equation
> By combining the Sigmoid Function with the previous output equation, we can get a new equation that only depends on weight, value, and bias:
> $$\frac{1}{1 + exp(-\sum^j_{i=0} w_ix_i - b)}$$
>($exp(x)$ is $e^{x}$)

> [!example] 
> We can show that Sigmoid neutrons won't output anything outside of the bounds of 0 and 1. 
> >For example, if $w⋅x+b$ is a super-high positive value:
> >$$\frac{1}{1 + exp(-\infty)} \approx \frac{1}{1 + 0} = 1$$
> >
> >When $w⋅x+b$ is very negative:
> >$$\frac{1}{1 + exp(\infty)} \approx \frac{1}{1+\infty} = 0$$
> For any other more moderate values, $σ(w⋅x+b)$ would be in between.

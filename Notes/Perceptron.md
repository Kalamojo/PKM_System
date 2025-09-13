---
aliases: []
tags:
  - personal
---
# Perceptron

> [!note]
>Perceptron [[Neurons]] take several [[Binary]] inputs and produce a single binary output. 

> [!example] 
> ![[Drawing 2021-11-12 15.29.26.excalidraw|600]]

> [!info]
> To compute those outputs, various [[Weight|Weights]] are used. This process takes all the weights, multiplied by their associated binary values, to create a [[Weighted sum]]. In any given perceptron, if the weighted sum of all their inputs is $\leq$ to their threshold, it will return a 0. Likewise, if the weighted sum of the inputs is > the threshold, the perceptron will reeturn a 1. 
> Alternatively, the threshold can be subtracted from the weighted sum, and then compared to 0 like so:
> 
> > [!math]
> > 0 if $\sum^j_{i=0} w_ix_i + b \leq 0$
> >  1 if $\sum^j_{i=0} w_ix_i + b > 0$
> >
> > >The $b$ represents the [[Bias]] of the perceptron, which is equivalent to the negative of the threshold.
> 
> This process occurs over and over, depending on the amount of [[Neural Layer|Neural Layers]] in the [[Neural Network]]. The only difference between one perceptron and the next is the weights attached to its connections.

> [!example] 
> ![[Drawing 2021-11-11 16.47.04.excalidraw|650]]
> In this image, what looks like multiple outputs is really just the same output being fed to multiple perceptrons. In this way, multiple other perceptrons can be influenced by just one.
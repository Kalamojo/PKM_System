---
alias: []
tags: [personal]
---
# Generalization

> [!note]
>$h\epsilon H$ such that $\forall(x, y)\sim P$, $h(x)\simeq y$. In other words, the given function can find the approximate relationships between inputs and outputs most of the time, or generally.
 > > [!math]
 > > $P=$ population or distribution

## Generalization Error

> [!math]
># $$E = [\ell(h_i(x, y))]_{(x, y)\sim P}$$
>$E=$ the Expected loss
>$\ell =$ [[Notes/Loss Function]]

This is a measure of how poorly a function acts on a distribution from a given population. Generalized functions will have a small $E$ value.

## Approximation

The expected loss is what we would love to minimize but can't because we don't know the entire population. While we can't compute it, we _can_ approximate it.

> [!example]
 > ![[Drawing 2021-12-16 13.38.30.excalidraw|center|700]]

By evaluating the function's success on the Test data, the Generalization error can be approximated.

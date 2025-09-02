---
alias: []
tags: academic
type: note
---
# Variational Autoencoder Improvement

From what I understand, variational autoencoders are simply weird autoencoders used for generating [[Data]] rather than learning more about the original data.

Autoencoders take input data, [[Encoder|encode]]  it to a dense representation, and then [[Decoder|decode]]  it to regenerate the original data. This sounds useless at first glance, but once an autoencoder is good at this process, we can learn a lot about their encoded data. Similar to Principal Component Analysis (PCA), these encodings are great for [[Dimensionality]] reduction, a useful [[Notes/Representation Learning|representation]] for training models and gaining general insights about data.

Variational Autoencoders also train to be good at this process of encoding and decoding. However, when making "predictions", they alter data at the encoded stage to reproduce a variant of their original data that is "unique".

The process of [[Notes/Training|training]] Variational Autoencoders, however, is slightly different from standard Autoencoders. With Autoencoders, how encodings are represented isn't terribly important (in some cases). As long as the model successfully reduces data to a form that can be regenerated, the model is rewarded.

![[Variational Autoencoder Improvement 2022-09-18 20.54.36.excalidraw|center|700]]

However, for Variational Autoencoders, simply recreating original data is not enough. The encodings need to be generalizable to create new variations. Instead of  simply defining loss as the difference between $x$ and $x'$, loss also takes into account the [[Difference]] between the encoding distribution and a [[Standard Normal Distribution|standard Gaussian]].

![[Variational Autoencoder Improvement 2022-09-18 21.14.07.excalidraw|center|700]]

## References
1. [[@lotfollahi.etal_2020]]

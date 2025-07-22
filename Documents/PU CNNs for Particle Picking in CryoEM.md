# PU CNNs for Particle Picking in CryoEM

## Overview

This paper introduces a method of particle picking developed by Topaz for CryoEM. Instead of a classic binary classification model to predict particle vs. non-particle regions on a micrograph, this model only requires a few sparsely labelled particles  in the data to train, eliminating the need of any negative labels and allowing training on mostly unlabeled data.

Not only does this positive-unlabeled learning method work with incomplete labels, but it actually ends up performing much better than conventional approaches. Topaz even takes this method a step further, utilizing novel optimization metrics to minimize model overfitting. The result is a particle picking predictions that are well-ranked and contain few false positives.

## Model Training

Positive-unlabeled (PU) learning is the training of a model with data that only contains some incomplete positive labels and no negative labels. It relies on the assumption that given a couple examples of what is *right*, you can reason about and make predictions on what isn't in an almost self-supervised way.

> [!example]
> ![[Pasted image 20230829220034.png]]
> Here is an example of what a positive-unlabeled dataset might look like. For the task of identifying dogs in a picture, rather than needing to label every dog as a positive example, and every cat or empty space in the room as a negative example, only a few positive examples, dogs, need to be labeled.

However, another crucial piece of the data, and a primary factor in a model's training, is the fraction of positive examples in the unlabeled data, $\pi$.

### Treat all unlabeled as negatives

One very basic PU technique is to treat all unlabeled samples as negative examples, allowing the application of a standard binary classification optimization. While this method can be effective if $\pi$ is small, meaning that the positive examples are mostly separated from unlabeled ones, it suffers from overfitting otherwise.

![[Pasted image 20230829220034.png]]

If we take this example of the dogs and cats again, the basic PU technique would assume the 3 dogs labeled are the only dogs in the image, and that everything else is not a dog. So when faced with an example outside of training, the model would have overfitted far too much to identify more than a few dogs.

### Constrain classifier to predict a similar distribution of positives to $\pi$

The proposed PU technique in this paper instead relies heavily on the ratio $\pi$ to train the classifier. It has two major points:

1. Loss is calculated based on how the model performs on the positively labeled samples
2. The classifier is constrained to produce a similar ratio of positive predictions to $\pi$, the true ratio of positive examples in unlabeled data

With these two guidelines, overfitting is substantially reduced and the classifier is able to train with incomplete positive labels and no explicit negative labels.

## Model I/O

Strides are used to provide sliding micrograph inputs to the CNN model. The predictions are then compared to the few labeled positive regions of the original data, and based on those, the model learns to improve.

![[Pasted image 20230830223117.png]]

For predictions, a similar sliding approach is used to retrieve CNN predictions for each region of a micrograph. These predictions are then passed to a non-maximum suppression algorithm to obtain coordinates of picked protein particles.

![[Pasted image 20230830223140.png]]

## Note-worthy

By itself, Topaz's particle picking ranks well compared to conventional particle picking methods, and even outperforms other positive-unlabeled trained models. But it's important to note that these results came from only 1,000 labeled examples and no filtering of micrographs, displaying the immense potential and robustness of this method.

## References
1. [[@beplerPositiveunlabeledConvolutionalNeural2019]]
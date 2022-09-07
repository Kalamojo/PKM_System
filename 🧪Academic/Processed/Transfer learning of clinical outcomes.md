---
alias: [Transfer Learning]
tags: academic
type: note
---
# Transfer learning of clinical outcomes

> [!summary] 
> Transfer Learning is an extremely useful tool in the field of medicine due to it's ability to make use of data not easily available. For example, obtaining brain tissue to test on and draw conclusions about medical conditions is not often feasable. Or as another example, while extensive experiments can be conducted on mice with high efficiency, the same is not true for humans, the true target of those results. Transfer Learning solves this issue by making use of more accurate data (ie brain tissue -> mental conditions, mouse genetic expressions -> responses to treatments) and transferring that information to make predictions on a target domain (blood data -> mental conditions, human gene expressions -> treatment responses).

## Semi-supervised Transfer Learning

> [!method] 
> The most precise method for learning human label predictions (from labeled mouse data) was using a semi-supervised neural net to iteratively "combine" the human data with the mouse data. As an analogy, imagine a model that is really good at guessing if a mouse is sick. You want it to be able to determine if a human is sick. So what you do is you keep the same model except when you are about to test on the human data, you first change them to their mouse "equivalent". That way, a model that is good at predicting on mice will still perform well on your artificial "mice".

![[Transfer Learning Visualizations#Semi-supervised Transfer Learning Visualization]]

## AITL

> [!method] 
> Labels exits for both the source domain and the target domain. The objective of AITL is to learn how labels in the target domain can be easily calculated. Instead of simply using the target data and labels alone for training (due to a lack of data), a multi-class model is trained on the source domain data at the same time. Common features are learned from this process. It is these features that are then used to train a model further on the source domain, which can then be used for the target domain.

![[Transfer Learning Visualizations#Adversarial Inductive Transfer Learning Visualization]]

## PRECISE

> [!method] 
> To find common molecular factors between the source data and the target data, a technical comparison is made using Principal Vectors (PCA). Once these common factors are determined, a model (using these factors) is trained on the source domain and later used to make predictions for the target domain. This has a similar concept to AITL.

![[Transfer Learning Visualizations#Patient Response Estimation Corrected by Interpolation of Subspace Embeddings Visualization]]

## trVAE

> [!method]
> This is an unsupervised learning approach using an autoencoder. An autoencoder is an unsupervised neural network that takes an input, passes it through a bottleneck layer, and tries to recreate the input. The same approach is applied in this paper, except with a twist. The autoencoder receives an input but also paired with a condition (like smiling or not smiling). The data passes through the bottleneck layer like usual, but before the model tries to decode it, it needs a condition again. For training, the autoencoder is fed correct pairings for conditions (i.e smiling image + smiling condition -> smiling condition, frowning image + frowning condition -> frowning condition). For testing, however, the condition is switched for a set that has no data (i.e smiling image + smiling condition -> frowning condition). In this way, target data is automatically transferred to a source data representation. Similar to Semisupervised Transfer Learning.

![[Transfer Learning Visualizations#Conditional Out-of-Distribution Transfer Learning Visualization]]

## References
1. [[@axelkowald.etal_2022]]
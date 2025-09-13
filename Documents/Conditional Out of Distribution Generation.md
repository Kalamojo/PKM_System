---
aliases:
  - Transfer VAE
tags: academic
type: note
---
# Conditional Out of Distribution Generation

> [!summary] 
> One effective method of modifying data to resemble a completely different domain is to assign classes to inputs and train a model to reproduce an those same inputs given their classes. This transfer learning method makes use of a Variational Autoencoder that takes an input + the class of the input, and tries to reproduce the original input.
> A previous model, the Conditional Variational Autoencoder (CVAE), utilized this method by taking an input + class, encoding both, and then taking the encoding + class to try and decode into the original input. While this method is adequate at transfering attributes from one [[Dataset|dataset]] to another, it doesn't internally relate conditions to inputs. Since a class is always provided seperate from the encoded input at the decode stage, the model struggles with learning how the input relates to the class.
> Enter the Transfer Variational Autoencoder (trVAE). This model is mostly identical to the CVAE, except for a major addition: regularization of the encoded input + class. By conceptually "mixing" these together right before decoding, to the point where the model has difficulty differentiating the two, the model is incentivised to encode the input in  such a way that only fundamental *non-class* related information is retained. For example, when encoding the image of a man smiling, paired with the class "smiling", encoding learns to essentially strip the man of his smile in preparation of mixing with the later supplied class. This differs from the original CVAE method, where the man could be encoded with *all* information, even smiling.
> By stripping an input of it's class-related information, encoded inputs are primed and ready to be supplied with a class and transformed.

## Out of Distribution Generation

Out of [[Distribution|distribution]] generation (OOD) is the generation of data with specific attributes without ever explicitly training on that kind of data.
For example, using a model to predict how a brown dog would look like with black fur becomes an OOD problem if the model is never trained on images of black dogs.

Initially, this may seem like an impossible task. However, by learning about this class of data (dogs with black fur) by training on one part at a time, it can be achieved.
The model could be trained on dogs with brown fur. Then, it is trained on cats with black fur. Finally, it is trained on cats with brown fur (to connect cat-related learning to dogs). With this information all stored in a model, it is reasonable to assume that the model is capable of generating an image of a dog with black fur.

While this makes sense conceptually, creating a model that can perform this OOD in practise can be difficult. Thankfully, the Transfer Variational Autoencoder (trVAE) was created to do just this.

## Variational Autoencoder

Variational Autoencoders are models that take inputs and try to reproduce them with variations. In the field of transfer learning, this usually means representating input data as data from a different [[Distribution|distribution]]. In other words, making data seem as if it comes from another domain.

For example, one could take an input image of a woman not smiling and place it in a Variational Autoencoder. This model may then produce an altered image of that same woman smiling.

Variational Autoencoders are also used to make minor modifications to data simply to anonymize data contributers. A dataset of the financial history of users, for example, could be changed in such a way that the identity of users remains undisclosed, yet general statistics about the data stay the same.

In the context of this paper, Variational Autoencoders are used for that first purpose: to transfer the domain of data.

## Conditional Variational Autoencoder

The Conditional Variational Autoencoder (CVAE) is a model that can transfer data from one domain to another using a [[Categorical Attributes|conditional variable]]. 
The inputs are your original data $x$ along with a condition $s_1$. Then, after the inputs have been encoded, another condition $s_2$ (or the same condition) is supplied with the encoding to be decoded into the transfered data $\hat{x}$.

> [!math]
> $\hat{z} = f(x, s_1)$
> $\hat{x} = g(\hat{z}, s_2)$
> - $\hat{z}$ = encoded (input with condition 1)
> - $\hat{x}$ = decoded (encoding with condition 2)

During training stages, the same conditions are used for both input steps, and the model learns to reproduce inputs given identical conditions. During the testing/transfer stage, the model is supplied a different second condition. If all went well, the model should produce data that closely resembeles data from that second condition.

This model is adequate for OOD (out of distribution) generation because it doesn't require training on a distribution to produce examples of it. By training on
- type one with class one, then 
- type two with class one, and finally 
- type one with class two,
 you can produce data with type two and class two.

## Limitations of CVAE

While the conditional variational autoencoder can successfully transfer data from one class to another, it faces a couple of limitations.
One is that he model could only train with two different classes at once. For example, for faces, you could have smiling and non-smiling classes. However, you couldn't have smiling, non-smiling, and winking classes.
There is another, more impactful limitation. The model suffers from innacuracy due to the fact that it doesn't internally relate conditions to data. For example, it doesn't "understand" that an inputed face with the class "smiling" is actually "smiling". 

> [!example]
> ![[Conditional Out of Distribution Generation 2022-10-17 18.12.15.excalidraw|center|800]]
> [[Visualization]] of how the CVAE takes inputs and produces outputs

Ignoring the class, this model will still perform "well" because its inputs resemble the outputs. In this dynamic where the model isn't forced to use the classes, it simply will not.
The model isn't incentivised to use the classes to combine with the encodings and change the outputs. By extension, encodings aren't incentivised be affected by classes because the decoding stage can simply select the correct features from the encoding.

## Transfer Variational Autoencoder

To address the limitations of the CVAE, the Transfer Variational Autoencoder was developed. It's key contribution is the introduction of a maximum mean discrepancy (MMD) layer right before decoding.
What this MMD layer does is essentially "mix" the encoding with the second class. This makes it extremely difficult for the model to ignore the class, forcing it to encode the input in a way that prepares it to be mixed with the class once more.

> [!math]
> $\hat{z} = f(x,s_1)$
> $\hat{y} = g_1(\hat{z},s_2)$
> $\hat{x} = g_2(\hat{y})$
> - $\hat{z}$ = encoded (input with condition 1)
> - $\hat{y}$ = mmd regularization of (encoding with condition 2)
> - $\hat{x}$ = decoded mmd regularization

This MMD layer is a sort of safeguard agains lazy activity by the model. In the CVAE model, the encoder and decoder can get away with ignoring the classes and still produce decodings similar to original inputs.
In the trVAE model, however, the decoder is forced to consider both the encoding and the second class. This thereby forces the encoder to create a more reasonable encoding: namely one that is void of all class-related information.

![[Pasted image 20221007091143.png]]

The reason why this is such a huge improvement from the CVAE is because encodings become primed and ready to be considered with classes. Smiling faces, encoded with the class smiling, become neutral faces. Black dogs, encoded with the class black, become dogs with no color.
WIth these internal representations, it becomes much easier for the encoding to then be "transfered" to a new domain given a class.

The trVAE also allows for training with multiple classes, addressing the second issue of the CVAE. It enables more robust and accurate transferring in OOD settings, and is a useful tool for transfer learning.

## References
1. [[@lotfollahi.etal_2020]]
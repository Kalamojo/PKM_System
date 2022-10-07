---
alias: [Transfer VAE]
tags: academic
type: note
---
# Conditional Out of Distribution Generation

> [!summary] 
> One effective method of modifying data to resemble a completely different domain is to assign classes to inputs and train a model to reproduce an those same inputs given their classes. This transfer learning method makes use of a Variational Autoencoder that takes an input + the class of the input, and tries to reproduce the original input.
> A previous model, the Conditional Variational Autoencoder (CVAE), utilized this method by taking an input + class, encoding both, and then taking the encoding + class to try and decode into the original input. While this method is effective in transfering attributes from one [[Dataset|dataset]] to another, it doesn't internally relate conditions to inputs. Since a clear class is always provided with the encoded input at the decode stage, the model struggles with learning how the input relates to the class.
> Enter the Transfer Variational Autoencoder (trVAE). This model is mostly identical to the CVAE, except for a major addition: regularization of the encoded input + class. By conceptually "mixing" these together right before decoding, to the point where the model has difficulty differentiating the two, the model is incentivised to encode the input in  such a way that only fundamental *non-class* related information is retained. For example, when encoding the image of a man smiling, paired with the class "smiling", encoding learns to essentially strip the man of his smile in preparation of mixing with the later supplied class. This differs from the original CVAE method, where the man could be encoded with *all* information, even smiling.
> By stripping an input of it's class-related information, encoded inputs are primed and ready to be supplied with a class and transformed.

## References
1. 
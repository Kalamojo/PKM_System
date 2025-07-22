# Senior Project Report

## Introduction

The technology behind Snapchat's anime filter is effective at transforming a face to appear as if from another class. Similar methods are also used for image editing, like removing wrinkles or beautification of a portrait. The overwhelming majority of the Machine-learning method of image transferring is by way of Generative Adversarial Networks (GANs). Input images are supplied to the generator, and after it alters the image, it is presented to the Discriminator to determine if the image belongs to the desired class or not. For a Generator to fool a Discriminator, all it needs to do is modify the pixels just enough to resemble the class of transfer.

While this works, and guarantees a high resemblance to the original image, its minimal transformations leave much to be desired. For our own attempt at image transferring, we make use of Transfer Learning, by way of an autoencoder, to transfer images to another class, specifically with a transfer variational autoencoder (trVAE). As opposed to the GAN approach, these transfers take an image, apply significant modifications, and attempt to recreate the image with a different label.

The primary motivation for the project was just to try and create Snapchat-like filters with a tool I was familiar with but in a completely different area. I wanted to try and make these transfers the way that I had previously thought image transferring worked instead of GAN approaches.

## Body of Work

### Setup

This project was created entirely in Python with Tensorflow and the Keras API. The paper from which this model originated contained a demonstration of Out-of-distribution transferring of not smiling to smiling women faces, and I used this as my starting code for the anime transferring model.

The most important part of creating predictive models is obtaining data to train on, and for this project, it was also the most difficult part. After much searching, and tests of model performance upon training, I was set on 3 datasets:

- CelebA dataset of celebrity faces,
- A Hugging Face anime faces dataset, and
- Google Cartoonset of cartoon faces

To understand why I selected 3 different datasets for training, I should describe how the trVAE trains.

### Training

True to Autoencoders, this model trains by taking inputs, encoding them, and decoding them to be identical to the original inputs. However, the Variational part of this trVAE lies in the labels images are concatenated with before the encoding and decoding steps. For example, a realistic image will be supplied to the encoder with the label "realistic" in the form of a vector of a repeated number (0 for the first label, 1 for the second, and so on). Then after encoding, before the reduced image is supplied to the decoder, another label is supplied to the reduced image, and only then is the image decoded.

During training, the model is supplied with the same label twice over and over. Realistic images are transferred to realistic, and anime images are transferred to anime. The evaluation metric for training the model is still as simple as comparing the input to the output.

While it may not be obvious how the model is learning to transfer images to another label, the magic lies in how the labels are combined with the images and the fact that the same model is trained to perform well on all classes. Before decoding a reduced image, the label is "mixed" with the image in the MMD layer. By mixing the label and image, the decoder model is unable to simply ignore labels to achieve high accuracy across all classes. This primes the encoder label to prepare an image to be supplied with a second label later. Here's my understanding of the process:

> For a smiling to not smiling transfer, the encoder is supplied a smiling image with the label smiling. It can choose to ignore the label smiling and encode the unaltered image, but then when the label smiling is mixed with the image before decoding, the output will be the original image but with lots of noise caused by label mixing. 
 
After training for a couple of iterations, the encoder realizes this, and it eventually changes its strategy to this:

> Given a label, "remove" this label from the image. So given an image with the label smiling, remove the smile from the image and encode it. This way, when the reduced image is inevitably mixed with the second label of smiling, the decoder can take this generic image and "make it smile". This way, given any class label, the model can somewhat accurately create the original image by taking a generic image and applying the original label again.

### Predictions

After all of this training for a label to the same label, the predictive step is fairly simple:

> Encode an image with the label "real", but instead of supplying the label real again for decoding, instead supply the label "anime". The image is then decoded to the anime version of the original image.

Because the encoder learned to strip an image of the supplied class, and the decoder learned to supply each label to a generic reduced image, an encoded image of any class can be decoded to any class, allowing us to transfer an image from any class to any other class the model trained on.

To truly take advantage of this, I even added an extra class of cartoon images during training, and the beauty of this model is that adding more classes actually allows for improved accuracy of predictions. This is because the model needs to learn how the different labels contrast, and adding more contrastive labels improves the model's understanding of each.

## Project Management

I trained the model on 50,000 images from each dataset, making use of the UTRGV GPU clusters and running multiple variations of the model parameters. The result of training is a model that can take an image of either a realistic, anime, or cartoon label and transfer it to any of the 3.

I created a Streamlit application as a demo for the model, and it effectively transfers images from real to anime, or vice versa. I removed the option of transferring to and from cartoon labels because of some inaccuracies with that class, and to stay true to the original focus of the project.

I kept track of this project using a Jira board, making tickets for the model versions I wanted to train, and the basic tasks needed to create the demo website.

## Summary and self-evaluation

The primary limitation of the model is its requirement of closely cropped faces to make accurate predictions, a limitation that GANs do not suffer from nearly as much. This was partially a result of the training data I supplied to the model, but also a result of the model's ability to understand each class to make accurate transfers. To encode images to the latent space, the model needs to create an accurate representation of the original image, and it becomes far more difficult when there are distracting colors or objects in the background.

However, I was pleasantly surprised that this model worked at all. After running the paper's demo of smiling to not smiling transfers, I eagerly assembled datasets for a realistic to-anime transfer and was extremely disappointed by the results. The transferred images hardly resembled faces at all, and I had doubts as to whether this model could even handle transfers of such a novel task. However, after incorporating the full datasets, removing the out-of-distribution element of training, and messing around with the latent space size and learning rates, I was glad to see that the model truly worked.

In the future, I believe diversifying our training data will help to make the model more robust. I also hope to upload this model to TensorFlow hub to allow others to make use of it without needing to download it locally. The primary feature I want to add is the option for additional labels like "young" or "old" to see what a user might look like in the future, or might have looked like in the past. There are so many directions this project could take, and I really enjoyed exploring the few initial ones for this Senior Project.
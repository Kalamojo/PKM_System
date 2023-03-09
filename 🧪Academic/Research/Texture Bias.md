# Texture Bias

## Background

Before reading this paper, I was unfamiliar with optimization of machine learning models, and I didn't know the methods used to ensure that models learn exactly what creators want them to. Machine learning models seem like a black box of sorts, where inputs go in and, somehow, correct outputs come out. However, the insights of this paper have helped me to understand some key points about the nature of Neural Networks and ML in general.
In a sense, Machine Learning models are extremely lazy. Their only objective is to maximize some measure (usually accuracy) given choices to make based on information, and without any restrictions on *how* they maximize these measures, they often will develop the easiest technique possible. Because of this, simply looking at a model's accuracy score does not tell us how well the model has learned methods the same way we do, and this paper is a prime example of this.

## Papar Overview

At first glance, state of the art Convolutional Neural Networks (CNNs) seem to be prime examples of human-like thinking written in code. Depending on their data and duration of training, they are nearly 100% accurate in distinguishing and classifying images. However, while these magical black boxes certainly accomplish their tasks, their methodology was somewhat a mystery. With large neural networks taking inputs to functions, passing the outputs to other functions, and calculating the changes that need to be made in each funciton, it is not easy to understand exactly how a model can identify a cat, for example. The work of Geirhos et al. in 2018 made these methodologies much clearer:

> ![[intro_figure.png|center]]

Evidently, these CNNs trained to classify images had been accomplishing their tasks by simply looking at the texture of an figure. As Figure 1 (c) shows, even when an image that is obviously shaped like a cat is presented to the model, the model seemingly ignores that in favor of looking at the small patterns of lines and shapes that make up the cat's texture.
While this training may be sufficint in controlled environments with high quality images, the danger may come in applying these models in the real world. Strange lighting, low resulution cameras, or any number of factors may affect visibility of specific features, rendering these models innefective. For this reason, efferts were made to help models learn to identify images by using shape rather than texture.
The solution to this problem was quite simple:
- Distort training images in a varying number of ways
- Randomize these distortions to force models to learn generalizable features

> ![[example_stylization_imgs.png|center]]

These modifications reduce the probability that a model trained on this data "cheats" by learning small undesired patterns in the data. For a model to score accurately on each one of these distorted images, it needs have a fundamental understanding of shape and how that determines the subject of classification.

## Results

While there was a slight dip in performance, for tests run on the original images only, of models trained on these modified image datasets, their generalizibality increased substantiallly. Given distorted images to classify, models trained on "stylized" data outperformed top of the line models by a wide margin (results can be found [here](https://arxiv.org/pdf/1811.12231.pdf#section.3)).

# Transfer Learning cryo-EM Particle Classifier

## Overview

There are two primary forces at work in this paper:

1. The application of transfer learning to train a cryo-EM classifier from general image data
2. The employment of a multi-loss strategy to fine-tune the [[Classification|Classifier]] on little domain-specific data

By utilizing both, a cryo-EM classification model is able to be trained with limited cryo-EM data.

## Data Preparation

Due to limited cryo-EM data availability, and the tedious nature of protein reconstruction, it is difficult to train high-performing models with a standard approach. To address this limitation, Transfer learning can be used to train models from more abundant [[Data]], yet still apply that training for the desired domain.

In this case, the primary [[Dataset]] for training is ImageNet, a widely used large-scale dataset with about 1.2 million images from 1000 different categories. The knowledge gained from learning object detection in these generic images is then used to detect particles in cryo-EM images.

![[imagenet_banner.jpeg]]

However, these two tasks are not perfectly analogous, and so to help facilitate the transfer of knowledge, the ImageNet dataset is combined with 3600 cryo-EM image samples spanning 36 different categories with positive and negative samples alike (some containing particles and others containing particle-like structures).

## Multi-loss Strategy

The primary issue with [[Notes/Training|Training]] a model on limited data is [[Overfitting]]. [[Machine Learning Model|Models]] essentially perform well on the data they were trained on, and don't generalize well to new data. The selected method of combating this overfitting is to make use of multiple [[Notes/Loss Function|Loss Functions]] to train the same model.

To even obtain multiple loss values, multiple tasks need to be performed to measure performance from. However, in a classification model, it is not obvious how to derive multiple useful tasks a model can perform. This is how the task of object/particle detection is transformed into two tasks:

>[!method] 
> - The main task or "branch" has a classic architecture where the feature map is passed to a classifier model, and then a class prediction is made.
> - A secondary branch is added, which is just like the first except that before the feature map is passed to the classifier, it passes through a 1 by 1 convolutional layer that reduces the [[Dimensionality]] of the feature map.

![[Pasted image 20231108220635.png]]

The performance of both branches are measured, giving the model two different loss functions to learn from. This way, the model is much less likely to overfit to just one loss function, and yet is still learning to perform well for the same underlying purpose.

## Training Method

The training stage is divided into 2 phases: [[Pre-Train|Pre-Training]] and fine-tuning.

In the Pre-Training phase, a combination of the ImageNet and cryo-EM data is used to train the model before anything else. For Fine-tuning, the remaining cryo-EM is utilized.

## References
1. [[@liTransferLearningBasedClassification2022]]
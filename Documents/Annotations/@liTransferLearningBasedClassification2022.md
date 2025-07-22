---
alias: A Transfer Learning-Based Classification Model for Particle Pruning in Cryo-Electron Microscopy
authors: Hongjia Li, Ge Chen, Shan Gao, Jintao Li, Xiaohua Wan, Fa Zhang
year: 2022
type: paper
tags: academic
page(s): 
---
> [!abstract]
> The cryo-electron microscopy (cryo-EM) single-particle analysis requires tens of thousands of particle projections to reveal structural information of macromolecular complexes. However, due to the low signal-to-noise ratio and the presence of high contrast artifacts and contaminants in the micrographs, the semiautomatic and fully automatic particle picking algorithms tend to suffer from high false-positive rates, which degrades the confidence of structure determination. In this study, we introduce PickerOptimizer (PO), a transfer learning-based classification neural network for particle pruning in cryo-EM, as an additional strategy to complement the current automated particle picking algorithms. To achieve high classification performance with minimal human intervention, we adopted two key strategies: (1) utilizing the transfer learning techniques to train the convolutional neural network, where the knowledge gained from public classification datasets is applied to the field of cryo-EM. (2) Designing a multiloss strategy, a combination of multiple loss functions, to guide the optimization of the network parameters. To reduce the domain shift between cryo-EM images and natural images for pretraining, we build the first image classification dataset for cryo-EM, which contains positive and negative samples collected from EMPIAR entries. The PO is tested on 14 public experimental datasets, achieving accuracy and F1 scores above 95% in most cases. Furthermore, three case studies are provided to verify the model performance by applying PO on problematic particle selections, showing that our algorithm achieved better or comparable performance compared with other particle pruning strategies.

# Annotations  
(11/7/2023, 9:08:52 PM)

“the CNN is first pretrained with a combination of a natural image dataset and a cryo-EM image dataset, and then fine-tuned with only a few manually labeled samples from the new dataset to adapt to new features.” ([Li et al., 2022, p. 1118](zotero://select/library/items/C9XU76JD)) ([pdf](zotero://open-pdf/library/items/5ZR3AC62?page=2&annotation=KDVJHT4X))

“we design a multiloss strategy for PO, where a combination of loss functions simultaneously guide the updating of model parameters.” ([Li et al., 2022, p. 1118](zotero://select/library/items/C9XU76JD)) ([pdf](zotero://open-pdf/library/items/5ZR3AC62?page=2&annotation=WMEXDP3X))

“Compared with the ordinary classifier that contains only one branch to directly transform the feature map obtained from feature extractor to a category vector, we add a new branch to compress the dimension of the feature maps to half of the previous size using a 1\*1 convolutional layer. The feature maps are optimized on two branches, respectively, and the generated gradients jointly update the network. In this way, a classification task is split into two tasks with the same goal.” ([Li et al., 2022, p. 1121](zotero://select/library/items/C9XU76JD)) ([pdf](zotero://open-pdf/library/items/5ZR3AC62?page=5&annotation=PKNRKFYM))

“For the natural one, we chose one of the most widely used large-scale datasets for benchmarking image classification algorithms, ImageNet (Deng et al., 2009) here. The dataset contains about 1.2 million images and is divided into 1000 categories” ([Li et al., 2022, p. 1122](zotero://select/library/items/C9XU76JD)) ([pdf](zotero://open-pdf/library/items/5ZR3AC62?page=6&annotation=I2B7DNAL))

“we constructed a cryo-EM dataset for image classification to enable the model to learn the image features specific to cryo-EM. The dataset contains positive samples (particles) and negative samples (carbon or icecontaminated regions) manually selected from 14 different EMPIAR entries, as shown in Table 1. The whole dataset contains 3600 images and is divided into 36 categories (14 kinds of particles, 14 kinds of high-contrast contaminants, and 8 kinds of carbon regions) with 100 images in each category” ([Li et al., 2022, p. 1122](zotero://select/library/items/C9XU76JD)) ([pdf](zotero://open-pdf/library/items/5ZR3AC62?page=6&annotation=KCDUCK6D))

“To avoid crossover between the dataset for pretraining and training, in the Results section, the datasets for pretraining only contain 13 datasets from Table 1, and the remaining one dataset is used for model training (fine-tuning) and evaluation” ([Li et al., 2022, p. 1123](zotero://select/library/items/C9XU76JD)) ([pdf](zotero://open-pdf/library/items/5ZR3AC62?page=7&annotation=2BUGG2MJ))

## References
1. [liTransferLearningBasedClassification2022](zotero://select/items/@liTransferLearningBasedClassification2022)

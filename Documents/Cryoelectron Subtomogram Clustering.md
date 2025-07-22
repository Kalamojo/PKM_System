# Cryoelectron Subtomogram Clustering

## Overview

To detect which molecule structures are similar to others, biomedical images are transformed into lower-dimension vectors. These vectors can then be grouped though unsupervised methods, and vectors belonging to the same clusters are labeled as such. The now labeled vectors can be transformed back to their original structures through backpropagation and compared for further review.

## Background

While methods already exist for detecting molecule structures, many of these rely on existing labeled data for past examples of macromolecules in tomograms. Apart from relying on labeled data, these methods are very low-throughput. If a section of a tomogram must be compared to every type of labeled structure, even with vector optimization and many comparisons at once, that's a lot of processing needed. To address these issues, a Deep Iterative Subtomogram Clustering Approach (DISCA) is introduced.

## Method

To make the tomogram sections more comparable with statistical methods, a tomogram is passed through a Convolutional Neural Network, effectively producing feature vectors. The resulting vectors can then be compared by way of Pearson Correlation, K means clustering, or any other statistical comparison method. Groups are formed, and the assumption is that every group of features represents one subtomogram of a macromolecule from the original image. Each group is then labeled as such, denoting the various subtomograms.

> ![[228112212-f1ed62f5-5c7d-4c34-8614-37ee4f58f045.png|center|340]]

Through backpropagation, while still recording the labels of each feature vector, the original tomogram is reconstructed, but now with group labels that divide the tomogram into similar sections. Each section should represent a different macromolecule, all of which were obtained at an extremely high rate and without labeled data.
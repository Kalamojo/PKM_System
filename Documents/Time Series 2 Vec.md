# Time Series 2 Vec

## Background

Anomaly detection, and various other Time-series specific tasks, strike me as far more nuanced than taks specific to other data-types. While a model can train on many images from differeing sources to improve image [[Classification|classification]], for example, the same cannot be said for [[Anomaly Detection]]. A peak in values in one time series may mean something completely different than another. To determine if a certain data point is unusual, only that time series can be used to make a judgement. This specificity makes time-series specific tasks often much different, and more complex, than various other tasks. That's why a model for automatically generating embeddings for time-series data, which can be used in any number of tasks, strikes me as incredibly promising.

## Paper Overview

There are two key steps that are used to generate these embedding vectors in an [[🧪Academic/Saved/Unsupervised Learning|unsupervised]] manner:
1. Contrastive Consistency measurements at the instance level
2. Hierarchical Contrasting to obtain unified embedding

### Contrastive Consistency

The contrastive consistency step obtains the embedding for small portions of a time series by obtaining ground truth on positive and negative samples.

> ![[Pasted image 20230430222959.png|center|500]]

Given an instance of a time series, a crop is applied to create 2 sub-instances. The area where the sub-instances overlap should produce similar embeddings, while the areas where they differ should produce different word embeddings. This is the basis of the positive and negative pairs for unsupervised learning:

- The model is trained to produce similar embeddings for positive pairs
- It is also trained to produce different embeddings for negative pairs

Once the model has trained on both of these tasks, it effectively generates embeddings at the instance level of time-series data.

### Hierarchical Contrasting

Once the embeddings are obtained for each instance of a time series, they are then leveraged to find the embeddings of larger sections of the time-series though maxpooling. N instances are combined to create n/2 larger sections. Those sections are combined to make n/4 sections. This process is repeated until finally, the embeddings of two sections are used to create the final embedding of the entire time series.

> ![[Pasted image 20230430232929.png|center|700]]

## Results

Not only did this method provide an efficient unsupervised method of generating word embeddings, but it also improved the accuracy of forecasting, classification, and anomaly detection when it's embeddings were utilized.
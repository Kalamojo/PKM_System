---
alias: Positive-unlabeled convolutional neural networks for particle picking in cryo-electron micrographs.
authors: Tristan Bepler, Tristan Bepler, Andrew Morin, Micah Rapp, Julia Brasch, Lawrence Shapiro, Alex J. Noble, Bonnie Berger
year: 2019
type: paper
tags: academic
page(s): 1153–1160
---
> [!abstract]
> Cryo-electron microscopy is a popular method for the determination of protein structures; however, identifying a sufficient number of particles for analysis can take months of manual effort. Current computational approaches find many false positives and require ad hoc postprocessing, especially for unusually shaped particles. To address these shortcomings, we develop Topaz, an efficient and accurate particle-picking pipeline using neural networks trained with a general-purpose positive-unlabeled learning method. This framework enables particle detection models to be trained with few sparsely labeled particles and no labeled negatives. Topaz retrieves many more real particles than conventional picking methods while maintaining low false-positive rates, is capable of picking challenging unusually shaped proteins (for example, small, non-globular and asymmetric particles), produces more representative particle sets and does not require post hoc curation. We demonstrate the performance of Topaz on two difficult datasets and three conventional datasets. Topaz is modular, standalone, free and open source ( http://topaz.csail.mit.edu ).

# Annotations  
(8/29/2023, 6:10:00 PM)

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=1&annotation=54QGXD5V) “This framework enables particle detection models to be trained with few, sparsely labeled particles and no labeled negatives.” ([Bepler et al., 2019, p. 1](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=2&annotation=G6FFHYCD) “Moreover, the diverse characteristics of negative data make it difficult to manually label a representative set of negative examples, and hence the number of labeled negatives must be an order of magnitude larger than the number of positives to achieve acceptable performance15. This has limited adoption by the cryoEM community and hand-labeling remains the gold standard.” ([Bepler et al., 2019, p. 2](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=2&annotation=QYWVCLGQ) “We seek to learn a classifier of positives and negatives given a small number of labeled positive regions and the remaining unlabeled regions.” ([Bepler et al., 2019, p. 2](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=2&annotation=G7Q4Y3QJ) “but overfitting remains a challenge for PU learning19” ([Bepler et al., 2019, p. 2](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=2&annotation=EVFFKZ9L) “Therefore, we instead approach PU learning as a constrained optimization problem in which we wish to find classifier parameters to minimize classification errors on the labeled data subject to a constraint on the expectation over the unlabeled data.” ([Bepler et al., 2019, p. 2](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=2&annotation=MHRYXGWP) “By imposing this constraint softly with a novel generalized expectation (GE) criteria20, we are able to mitigate overfitting and train high accuracy particle classifiers using very few labeled data points.” ([Bepler et al., 2019, p. 2](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=9&annotation=G7F4KD27) “When π is small, treating the unlabeled examples as negatives for the” ([Bepler et al., 2019, p. 9](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=10&annotation=E9HAICGZ) “purposes of classifier training with the following standard loss minimization objective, for suitable cost function L, can be effective πEx ∼ P L g x , 1 + 1 − π Ex ∼ U L g x , 0)]” ([Bepler et al., 2019, p. 10](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=10&annotation=PZDSXSNR) “Kiryo et al.19 recently proposed an unbiased estimator of the true positive-negative classification objective for positive and unlabeled data with known π and a non-negative estimator (PU) which is shown to reduce overfitting still present in the unbiased estimator.” ([Bepler et al., 2019, p. 10](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=10&annotation=DYWRJC8B) “Instead, we observe that the unlabeled data with known π can be used to constrain a classifier such that it minimizes the classification loss on the labeled data and matches the expectation (π) over the unlabeled data. In other words, we wish to find the classifier, g, that minimizes Ex∼P[L(g(x),1)] subject to the constraint Ex∼U[g(x)] = π. This constraint can be imposed “softly” through a regularization term in the objective function with weight λ: Ex ∼ P L g x , 1 + λKL Ex ∼ U g x ∨ π” ([Bepler et al., 2019, p. 10](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=10&annotation=8BN9X5A2) “we propose an alternative GE criteria, GE-binomial, defined so as to minimize the difference between the distribution over the number of positives in the minibatch and the binomial distribution parameterized by π. The number of positive data points, k, in a minibatch of Nsamples from U follows the binomial distribution with parameter π.” ([Bepler et al., 2019, p. 10](zotero://select/library/items/GJ6FQ632))

[Go to annotation](zotero://open-pdf/library/items/IN8I8UBC?page=19&annotation=QY5ZJFCF) “Once the CNN classifier is trained, particles are predicted in two steps. First, the classifier is applied to each micrograph region to give per region predictions. Second, coordinates are extracted from the region predictions using nonmaximum suppression.” ([Bepler et al., 2019, p. 19](zotero://select/library/items/GJ6FQ632))

## References
1. [beplerPositiveunlabeledConvolutionalNeural2019](zotero://select/items/@beplerPositiveunlabeledConvolutionalNeural2019)

---
alias: Conditional out-of-distribution generation for unpaired data using transfer VAE.
authors: Mohammad Lotfollahi, Mohsen Naghipourfar, Fabian J. Theis, Fabian J. Theis, F. Alexander Wolf
year: 2020
type: paper
tags: academic
page(s): 
---
> [!abstract]
> MOTIVATION While generative models have shown great success in sampling high-dimensional samples conditional on low-dimensional descriptors (stroke thickness in MNIST, hair color in CelebA, speaker identity in WaveNet), their generation out-of-distribution poses fundamental problems due to the difficulty of learning compact joint distribution across conditions. The canonical example of the conditional variational autoencoder (CVAE), for instance, does not explicitly relate conditions during training and, hence, has no explicit incentive of learning such a compact representation. RESULTS We overcome the limitation of the CVAE by matching distributions across conditions using maximum mean discrepancy in the decoder layer that follows the bottleneck. This introduces a strong regularization both for reconstructing samples within the same condition and for transforming samples across conditions, resulting in much improved generalization. As this amount to solving a style-transfer problem, we refer to the model as transfer VAE (trVAE). Benchmarking trVAE on high-dimensional image and single-cell RNA-seq, we demonstrate higher robustness and higher accuracy than existing approaches. We also show qualitatively improved predictions by tackling previously problematic minority classes and multiple conditions in the context of cellular perturbation response to treatment and disease based on high-dimensional single-cell gene expression data. For generic tasks, we improve Pearson correlations of high-dimensional estimated means and variances with their ground truths from 0.89 to 0.97 and 0.75 to 0.87, respectively. We further demonstrate that trVAE learns cell-type-specific responses after perturbation and improves the prediction of most cell-type-specific genes by 65%. AVAILABILITY AND IMPLEMENTATION The trVAE implementation is available via github.com/theislab/trvae. The results of this article can be reproduced via github.com/theislab/trvae_reproducibility.

# Annotations  
(9/27/2022, 9:08:41 PM)

“The canonical example of the conditional variational autoencoder (CVAE), for instance, does not explicitly relate conditions during training and, hence, has no explicit incentive of learning such a compact representation.” ([Lotfollahi et al., 2020, p. 610](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=1&annotation=UGGRCBZY))

“Now, predicting how a given brown dog would look like with black fur becomes an OOD problem if the training data does not have observations of black dogs.” ([Lotfollahi et al., 2020, p. 610](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=1&annotation=WVJ2RTTC))

([Lotfollahi et al., 2020, p. 610](zotero://select/library/items/KAV2IB38)) The trVAE is engineered to generate data for out-of-distribution (OOD) situations. These problems can be defined using 2 variables:  
- $s$: the category  
- $d$: the domain  
For example, untreated humans have this representation: ($s$=untreated, $d$=in vivo human). The trVAE doesn't require training data for ($s$=treated, $d$=in vivo human) to predict data of that class. This is made possible with $s$=treated data from different domains, like ($s$=treated, $d$=in vivo mouse) or ($s$=treated, $d$=in vitro human).

“In supervised domain adaptation approaches, MMD-based regularization has been shown to be a viable strategy of learning label-predictive features that are stripped off of domain-specific information (Long et al., 2015; Tzeng et al., 2014).” ([Lotfollahi et al., 2020, p. 610](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=1&annotation=K7I5VTMN))

“The approach of this article, however, introduces a data-driven end-to-end approach, which does not involve hard-coded elements and generalizes to more than one condition.” ([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=2&annotation=2LYWCQQ5))

([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) Autoencoders train by repetitively encoding data and reproducing it. This process leads them to find meaningful representations of their input data at the encoding level.  
Variational autoencoders, however, modify these representations in some way and still try and regenerate the original data. This leads to outputs that have inherent similarities to inputs while still being "original".

“The motivation of the VAE (Kingma and Welling, 2013) is to provide a neural-network based parametrization for maximizing the likelihood
$$p_\theta(X \mid S)=\int p_\theta(X \mid Z, S) p_\theta(Z \mid S) d Z$$ 
where $X$ denotes a high-dimensional random variable, $S$ a random variable representing conditions, h the model parameters and $p_\theta(X \mid Z, S)$ the generative distribution that decodes $Z$ into $X$.” ([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=2&annotation=JGAG3HVM))

“Consider the kernel-based estimate of a distance between two distributions $p$ and $q$ over the random variables $X$ and $X^\prime$. Such a distance, defined via the canonical distance between their $\mathcal{H}$-embeddings, is called the MMD (Gretton et al., 2012) and denoted $l_{\mathrm{MMD}}\left(p, q\right)$, with an explicit expression:
$$ \begin{aligned} \ell_{\mathrm{MMD}}\left(X, X^{\prime}\right)=& \frac{1}{n_0^2} \sum_{n, m} k\left(x_n, x_m\right)\\+\frac{1}{n_1^2} \sum_{n, m} k\left(x_n^{\prime}, x_m^{\prime}\right) &-\frac{2}{n_0 n_1} \sum_{n, m} k\left(x_n, x_m^{\prime}\right) \end{aligned} $$
where the sums run over the number of samples $n_0$ and $n_1$ for $x$ and $x^\prime$, respectively.” ([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=2&annotation=F7ZK3LXI))

([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) A GAN (generative adversarial network) is a competition between two neural networks where one generates data from input data and the other verifies the outputs. However, there's a catch: generated data should have the same statistics to the original inputs while still appearing as "original" data. When one model succeeds in generation, the other model is penalized for not catching the fake outputs. This network environment encourages rapid learning in both networks.

“High-dimensional observations x and a scalar or low-dimensional condition s are transformed using f (encoder, corresponding to distribution q/) and g (decoder, corresponding to distribution ph), which are parametrized by weight-sharing neural networks, and give rise to predictors $\hat{z}$,  $\hat{y}$ and $\hat{x}$: 
	$\hat{z} = f(x,s)$ (5a) 
	$\hat{y} = g_1(\hat{z},s)$ (5b) 
	$\hat{x} = g_2(\hat{y})$ (5c) 
where we distinguished the first ($g1$) and the remaining layers ($g_2$)of the decoder $g = g_{2} \degree g_1$ (Fig. 1).” ([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=2&annotation=2TA627DL))

![[Pasted image 20221007091143.png]]

“While $z$ formally depends on $s$, it is commonly empirically observed $Z \perp S$, that is, the representation $z$ is disentangled from the condition information s. By contrast, the original representation typically strongly covaries with $S\text{: } X \not\perp S$. The observation can be explained by admitting that an efficient z-representation, suitable for minimizing reconstruction and regularization losses, should be as free as possible from information about $s$.” ([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=2&annotation=T3VFYCTH))

“In the standard CVAE, without any regularization of this y representation, a highly varying, non-compact distribution emerges across different values of $s$ (Fig. 2). To compactify the distribution so that it displays only subtle, controlled differences, we impose MMD Equation 2 in the first layer of the decoder (Fig. 1).” ([Lotfollahi et al., 2020, p. 611](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=2&annotation=DWHXNQL7))

“During training time, all samples are passed to the model with their corresponding condition labels $(x_s,s)$. At prediction time, we pass $(x_{s=0},s=0)$ to the encoder $f$ to obtain the latent representation $\hat{z}_{s=0}$. In the decoder $g$, we pass $(\hat{z}_{s=0},s=1)$ and through that, let the model transform data to $\hat{x}_{s=1}$.” ([Lotfollahi et al., 2020, p. 612](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=3&annotation=U2X6TJBF))

“For training, we used all normal-stroke data. Hence, the training data covers all domains $(d \epsilon \{0,1,2,\ldots,9\})$ in the normal stroke condition $(s = 0)$. In the transformed conditions (thin and thick strokes, $s \epsilon \{1,2\}$), we only kept domains $(d \epsilon \{1,3,6,7\})$.” ([Lotfollahi et al., 2020, p. 613](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=4&annotation=NY3CEKQN))

![[Pasted image 20220927215617.png|center|500]]

“We focus on the task of learning a transformation that turns a non-smiling face into a smiling face. We kept the smiling ($s$) and gender ($d$) attributes and trained the model with images from both smiling and non-smiling men but only with non-smiling women.” ([Lotfollahi et al., 2020, p. 613](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=4&annotation=QV2IRR8J))

“In addition to showing the model’s capacity to handle more complex data, this example demonstrates the flexibility of the model adapting to well-known architectures like U-Net in the field.” ([Lotfollahi et al., 2020, p. 613](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=4&annotation=66TGT36R))

“trVAE successfully adds a smile on faces of women without a smile despite these samples completely lacking from the training data (OOD). The training data only comprises non-smiling women and smiling and non-smiling men” ([Lotfollahi et al., 2020, p. 614](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=5&annotation=E4ISLVPV))

“Finally, we note that architectures related to Gaussian mixture VAEs or GANs may be considered as alternatives to the MMD regularization.” ([Lotfollahi et al., 2020, p. 615](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=6&annotation=NVPAN2Q4))

“The ability to analyze and predict multiple perturbations allow trVAE to be applied to experiments with many biological conditions.” ([Lotfollahi et al., 2020, p. 615](zotero://select/library/items/KAV2IB38)) ([pdf](zotero://open-pdf/library/items/LMW786A8?page=6&annotation=8C6PZEKX))

## References
1. [lotfollahi.etal_2020](zotero://select/items/@lotfollahi.etal_2020)

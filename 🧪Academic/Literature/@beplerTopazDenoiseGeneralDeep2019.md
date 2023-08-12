---
alias: Topaz-Denoise: General deep denoising models for cryoEM
authors: Tristan Bepler, Tristan Bepler, Alex J. Noble, Bonnie Berger
year: 2019
type: paper
tags: academic
page(s): 838920
---
> [!abstract]
> Cryo-electron microscopy (cryoEM) is becoming the preferred method for resolving protein structure. Low signal-to-noise (SNR) in cryoEM images reduces the confidence and throughput of structure determination during several steps of data processing, resulting in impediments such as missing particle orientations. Denoising cryoEM images can not only improve downstream analysis but also accelerate the time-consuming data collection process by allowing lower electron dose micrographs to be used for analysis without compromising structural interpretability. Here, we present Topaz-Denoise, a deep learning method for reliably increasing the SNR of cryoEM images in seconds. By training on a dataset composed of thousands of micrographs collected across a wide range of imaging conditions, we are able to learn models capturing the complexity of the cryoEM image formation process. While this general idea has been deployed successfully in natural imaging, protein threading, and proteomics, it has yet to be applied systematically in cryoEM where the lack of ground truth signal has been a long-standing limitation. To address this, we make the key insight that forming paired, independent micrographs from even and odd camera movie frames enables us to train denoising models without observing ground truth signal. We demonstrate that our denoising model improves SNR by roughly 100x over raw micrographs and 1.8x over other methods. Notably, we show that denoising with our general model enables solving the first 3D single particle structure of clustered protocadherin, an elongated particle with previously-elusive views. Topaz-Denoise and pre-trained general models are now included in Topaz (https://github.com/tbepler/topaz), a free and open-source software package that focuses on particle picking, and has been integrated into the Appion cryoEM suite. We expect that Topaz-Denoise will be of broad utility to the cryoEM community for improving micrograph interpretability and accelerating analysis.

## References
1. [beplerTopazDenoiseGeneralDeep2019](zotero://select/items/@beplerTopazDenoiseGeneralDeep2019)

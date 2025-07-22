# Topaz-Denoise

## Overview

Cryo electron microscopy can benefit greatly from microgram denoising. Particle picking is made easier, less time is needed for analysis, less electron dosage would be necessary to produce quality micrograms.

Topaz-Denoise was introduced to fulfil that need, and it has even enabled completely new analysis of molecules. It makes use of a revolutionary Deep Learning training method introduced by the Noise2Noise paper, allowing high quality microgram denoising without the need of clean training samples.

## Method Inspiration

Topaz-Denoise relies on a method introduced by Noise2Noise, a general purpose denoising model. The fundamental idea of Noise2Noise can be represented by a simple example:

> Say you want to know the temperature of a room, but only have somewhat faulty thermometers with you. Their measurements are as follows:
> 
> $[65, 52, 76, 69, 85]$
> 
> A valid way of determining the real temperature of the room would be to find the number that minimizes the standard deviation with each faulty measurement. One way of doing this would be to find the median of the values:
> 
> $med([65, 52, 76, 69, 85]) = 69$
> 
> Another would be to find the mean of the measurements:
> 
> $\overline{[65, 52, 76, 69, 85]} = 69.4$

Similarly, the Noise2Noise model works by taking a noisy image and generating "faulty" versions by applying extra random noise. Then, given these versions, the model attempts to produce an image that minimizes the difference between it and each "faulty", noisy image.

![[Pasted image 20230811220022.png|center|250]]

Again, the assumption is that an output that is closest to every faulty or noisy version likely has very little derivation from the true value. The beauty of this method is that unlike a classic regression training, no "real" version is required to pair with the noisy images. Comparatively, these classic methods are almost akin to taking a faulty temperature measurement, then looking at the real temperature, and repeating this process again and again until the observer is able to predict the non-faulty version reliably.

## Topaz Implementation

Topaz-Denoise utilizes this method of denoising, but with a slight change that maximizes the use of existing cryoEM methods and measurements.

Instead of adding noise to obtain model inputs, "faulty" micrograms are obtained by simply organizing standard cryoEM movie frames of a given molecule. The frames are separated by whether they are odd or even in their ordering. Then, every "odd" frame is summed together into a single micrograph, as well as the "even" frames. The two resulting micrographs are the variations that are used to train the model.

The specific loss metric for this implementation compares the model's denoised "even" micograph to the summed "odd" micrograph. The denoised "odd" micrograph is in turn compared to the summed "even" micrograph. Both measurements of similarity are used to train the model.

![[Pasted image 20230811221744.png]]

## Impact

A similar method was used to develop a 3D version of this denoising model, which is actually the first general 3D denoising model for cryoET tomograms.

Additionally, by using this 3D model, along with Topaz particle picking, the very first 3D single particle cryoEM structures of clustered protocadherin, an elongated particle with previously elusive views and an unseen conformation, were obtained.

![[Pasted image 20230811222611.png|center|500]]

## Disclaimer

One important note to be made is that cryoEM/ET refinement and reconstruction software typically assume that micrograms contain noise distributions generally found in raw data, not denoised data. Secondly, denoised micrograms may present hallucinated information that is not detectable by visual inspection.

Therefore, by the Author's own recommendation, Topaz-Denoise should be used to assist with visualization and object identification primarily, if not exclusively. Then, detected objects should be extracted and processed from raw micrographs/tomograms.

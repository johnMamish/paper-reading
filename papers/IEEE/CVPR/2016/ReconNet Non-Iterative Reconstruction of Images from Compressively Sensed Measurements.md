## ReconNet: Non-Iterative Reconstruction of Images from Compressively Sensed Measurements
#### [[authors/Kuldeep Kulkarni Suhas Lohit]], [[authors/Pavan Turaga]], [[authors/Ronan Kerviche]], and [[authors/Amit Ashok]], 2016

#### Summary
Compressive sensing requires reconstruction of a signal which has been undersampled in a random domain. In the classical formulation of CS, this can be achieved precisely as long as the signals satisfy certain requirements, but these requirements are often only loosely met in practice, leading to reconstructions that take a prohibitively long time and yield unsatisfying results. The authors present a new CS reconstruction strategy.

In this work, the authors reconstruct images that are undersampled in a random domain. They do this in a block-wise fashion, first breaking each image up into a 33x33 block. They use a 6-layer CNN which they call "ReconNet" to reconstruct the image, followed by an off-the-shelf denoising filter. The size of the network's first layer depends on the sampling rate, so the network needs to be re-trained for each sampling rate. The sampling matrix is fixed and the network is trained on blocks taken from a relatively small set of images. They evaluate their system against several other reconstruction methods at various undersampling rates in simulation AND by photos taken with a real DMD-based single-pixel camera. At high undersampling rates, ReconNet outperforms other methods consistently.


#### Additional Comments
I'm interested in knowing how much implicit information about the world is encoded in the network. Does the network learn what a letter 'A' looks like and so is more likely to decode that? I strongly suspect that this is NOT the case (due to the small size of the training set and block-based image segmentation), but I would like to read further into the paper to know for sure.

ALSO: this paper is a GREAT SOURCE for references about CS decoders.

I'm less interested in CS decompression than CS compression - especially if it's about lowering the computational burden at the reconstruction side. However, what's possible in reconstruction determines what's possible at the sampling end, so I still need to keep tabs on this.

This is a very vanilla usage of a small CNN. Seems like an instance of playing "neural network" mad libs with a well-established problem, but the authors have written the paper well; explanation of the network is well done and evaluation is pretty complete.

Keywords: [[compressive-sensing]] [[deep-learning]] [[sparse-reconstruction]]
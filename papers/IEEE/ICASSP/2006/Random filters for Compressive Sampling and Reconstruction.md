## Random filters for Compressive Sampling and Reconstruction
#### [[authors/Joel A Tropp]], [[authors/Michael B Wakin]], [[authors/Marco Duarte]], [[authors/Dror Baron]], [[Richard Baraniuk]], 2006

#### Summary
Converting a signal to a sampling domain that's incoherent with a sparse representation domain - a key step in compressive sensing - requires a matrix multiplication which is O(NM). This restricts the applicability of compressive sensing in compute constrained devices. This paper aims to introduce methods for transforming a signal into a sufficiently sparse domain which take less computational power and storage.

The authors do this by passing the signal through a random filter - something that can be done 2 ways:
 1. With a traditional FIR filter - in this case, no computations are saved (O(MN) are still required), but this is well suited for streaming operations.
 2. By pairwise multiplication in the fourier domain - This takes substantially less computation (fast algorithms exist for fourier).
The authors evaluate their method by trying to use it to reconstruct some signals, which are generated to be sparse in different representation domains.

This work is an invitation to use compressive sensing in more computationally constrained environments. It also shows that random gaussian bases are not the only ones that can be used for CS.

#### Strengths
 * Significantly improves on the computational bounds implied in the initial CS paper.

#### Weaknesses
 * Not much evaluation relative to other methods

#### Additional Comments
This is one of the earliest works looking at ways to speed up compressive sensing. As far as I can tell, "Structurally Random Matrices" extends "method 2" of this work significantly in 2011.

#### What potential directions of future work remain?
This paper is described by the authors as "exploratory". Indeed, many other works in this document extend and more deeply explore the work done here by introducing

Keywords: [[compressive-sensing]] [[dsp]] [[keywords/digital-filters]]

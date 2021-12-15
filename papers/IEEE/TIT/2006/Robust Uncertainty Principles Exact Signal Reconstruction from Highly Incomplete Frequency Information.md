## Robust Uncertainty Principles: Exact Signal Reconstruction from Highly Incomplete Frequency Information
This paper lays the groundwork for compressive sensing. Compressive sensing is a follow-up to this paper.

#### [[authors/Emmanuel Candès]]and [[authors/Justin Romberg]], 2006

#### Summary
A lot of times, we're interested in a signal that's sparse (or more generally, has a small norm), but we can't observe it directly; instead, we only have sparse samples in the frequency domain (as in the motivating example of tomography, where a subset of fourier coefficients can be observed). Existing methods make naive guesses about the values of the missing Fourier coefficients, leading to reconstructions with tons of artifacts.

Can we still reconstruct the signal even though we fewer samples than the Nyquist rate?

The authors solve this problem by posing the reconstruction as a Linear Programming problem; to reconstruct a sufficiently sparse signal from a sparse set of fourier coefficients, you just need to find the signal with minimum l-1 norm that fits the Fourier coefficients. Of course, the reconstruction doesn't always succeed; the authors provide a bound for which the reconstruction will be correct with overwhelming (1 - O(1/(N^M)) probability.

The majority of the paper consists of a proof that the l1-norm based reconstruction method is exact given certain bounds. The authors also do some numerical experiments showing the dropoff in accuracy of the reconstruction for different levels of sparsity.

In section 6.3, "Extensions", the authors discuss how they're able to restore the 2-d "phantom" images which are NOT sparse in the spatial domain, but do have a small "total-variation" norm because they're composed of a bunch of step-function like ellipses. They strongly hint at general compressive sensing as a future direction by describing that this method can possibly be generalized to domains other than the spike and fourier domains.


#### What potential directions of future work remain (if any)?
Future directions are fulfilled by the compressive sensing paper, I guess.

Keywords: [[compressive-sensing]] [[sparse-reconstruction]] [[dsp]] [[convex-optimization]] [[linear-programming]]
Tags: [[foundational]] [[tags/highly-cited]]
## Compressed Sensing A Simple Deterministic Measurement Matrix and a Fast Recovery Algorithm

#### [[authors/Andrianiaina Ravelomanantsoa]], Student Member, IEEE, [[authors/Hassan Rabah]], Senior Member, IEEE, and [[authors/Amar Rouane]], 2015

#### Summary
Traditional transform-based lossy compression methods are often inappropriate for extremely computation-constrained systems. Compressive Sensing has offered promise in this area because it entails transformation into a randomly selected basis - which intuition tells you shouldn't be a computationally difficult task. Unfortunately, transforming a vector into a random Gaussian basis turns out to be computationally difficult, making this technique unsuitable for computation-constrained systems; looks like we're stuck with O(N * log(N)) DCT. Or are we? The authors propose a vector basis which, for the purposes of compressive sensing, is mathematically appropriate, but is very sparse (allowing for few operations) and is all binary (eliminating the need for multiplication). The use of the proposed matrix significantly lowers the computational burden on the encoder side. The matrix is similar to the one proposed in "The simplest measurement matrix for compressed sensing of natural images", but removes the permutation prescribed in that paper. The authors also provide a recovery algorithm for data collected in this manner which involves taking the IDCT of the data in the sensing domain.

The authors graph the coherence of their proposed sensing matrix (low coherence is important in compressive sensing) against an IDCT basis and show that it performs better than an I.I.D Gaussian matrix (a commonly used sensing matrix in compressive sensing). They also graph the reconstruction likelihood of their method given different levels of sparsity, showing that - in their pipeline - their matrix has a higher likelihood of recovery for less sparse signals than an I.I.D Gaussian or BPBD matrix.

#### Strengths
 * Implementation that discusses computational limitations of a real microcontroller
 * Seems to be very practical IRL for extremely computationally limited systems - something I've suspected but few papers actually try.

#### Weaknesses
 * Not much justification provided IMO for their IDCT treatment of signal in incoherent domain
 * Evaluation of their sampling matrix against other well-known ones is not apples-to-apples because they feed the data into their recovery pipeline, which is designed to work with their own sensing matrix.
 * Would've liked to see end-to-end collection of a real signal. How does amplifier noise affect?

#### Additional comments
Cool to see an actual, computationally limited impl of CS in the wild. I'm critical of their post-processing pipeline. Does it actually work? What's the basis? Also skeptical that their incoherence is that much better than I.I.D Gaussian.

Took theory and put it in hardware. Eval was adequate, could've been stellar.

#### What potential directions of future work remain (if any)?
Would like to see this evaluated on more types of signals.

Keywords: [[compressive-sensing]] [[hardware-implementation]]

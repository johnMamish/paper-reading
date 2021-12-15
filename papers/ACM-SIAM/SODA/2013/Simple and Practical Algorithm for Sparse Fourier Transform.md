## Simple and Practical Algorithm for Sparse Fourier Transform
#### Haitham Hassanieh, [[authors/Piotr Indyk]], [[authors/Dina Katabi]], Eric Price, 2013

#### Summary
FFT takes O(n * log(n)) time, which is pretty good. The problem with this is that we might want to take the DFT of a GIGANTIC signal, but we might only care about the largest k Fourier coefficients. Can we get sub-linear in n?

The method described operates by subsampling the given sample with stride sigma and offset tau. The authors use the FFT of the subsampled signal (which can be calculated quickly) to estimate the locations and magnitudes of the 'k' largest signals, which can be done with overwhelming probability in O(log(n)) subsample FFTs. Section 5.1 has some interesting info about runtime bounds in its last few paragraphs.

For very large FFTs where we're only interested in the k largest Fourier coefficients (for small k),the proposed method runs several orders of magnitude faster for some values of n (signal length) and k (sparsity). Moreover, accuracy of k largest values isn't significantly affected.

I'm interested in seeing how this method can be adapted to other problem domains than its original one. This algorithm is for taking the 1-d FFT of variable-length data on large systems. What about other transforms (2-d FFT, DCT, wavelet, hadamard)? What about fixed-length data (can we optimize more for fixed length data)? What about very small / low power-consumption systems?

#### Strengths
  * The paper makes a major theoretical contribution to DSP
  * The paper clearly describes the algorithm
  * The authors comprehensively evaluate sFFT against other algorithms over both constant sparsity and constant signal size.

#### Weaknesses
  * Some unclear notation, e.g. I think a modulo is missing in step 4 of the "inner loop" algorithm.
  * Need to dig through the paper to find discussion of key 'B' parameter.
  * Explanation of sFFT is extremely technical. An associated whitepaper or appendix with an easier to understand explanation would be helpful.

#### Remarks
This is a fundamental development in DSP algorithms and is well-presented

Keywords: [[compression]] [[keywords/dsp]] [[keywords/fourier-transform]] [[keywords/sparse-fourier-transform]]
Tags: 

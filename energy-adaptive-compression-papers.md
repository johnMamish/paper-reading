# DSP Theory
---
### Simple and Practical Algorithm for Sparse Fourier Transform
#### Haitham Hassanieh, Dina Katabi, et. al

From Katabi, one of the GOATs of DSP. Amazing.

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

#### Hot takes:
##### personal interest: 8/10

##### paper quality / novelty: 9/10
This is a fundamental development in DSP algorithms and is well-presented

### Fast and Efficient Compressive Sensing using Structurally Random Matrices
#### et. al

#### Summary
(A 2-4 sentence summary of the paper)
Background / Context: Sentence on the setting of the paper, broad placement in field, large societal reason for the paper.
Motivation / Problem: The one sentence summary of the problem this is tackling and why it is important.
Method: How they solve the problem (build a system? algorithm? study?)
Results: Whats the speedup, the outcome, the takeaway.
Future: This is for you to thoughtfully extend or engage the work and what it means.

#### Strengths
  * List strengths of the paper here
  * In a list format

#### Weaknesses
  * List weaknesses of the paper here
  * In a list format

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?


Hot takes:
personal interest: x/10
paper quality / novelty: x/10

* Design and Analysis of a Hardware-Efficient Compressed Sensing Architecture for Data Compression in Wireless Sensors

* Compressive Sensing on a CMOS Separable-Transform Image Sensor

* Sparse orthogonal matrices
    Cheon, Hwang, ... Song

* A FURTHER LOOK INTO COMBINATORIAL ORTHOGONALITY

* Image Compression Based on Compressive Sensing: End-to-End Comparison with JPEG

  * Adaptive Block Compressive Sensing: Toward a Real-Time and Low-Complexity Implementation

  *

  * A new wavelet based efficient image compression algorithm using compressive sensing

  * Compressive sensing based image compression-encryption using Novel 1D-Chaotic map

  * A Lecture on Compressive Sensing
    Baraniuk

  * An Introduction to Compressive Sampling

  * ADVANCES IN SPARSE SIGNAL ANALYSIS WITH  APPLICATIONS TO BLIND SOURCE SEPARATION AND  EEG/MEG SIGNAL PROCESSING
    PhD thesis by Nasser Mourad

  * The PhD student from Katabi's sFFT wrote a whole thesis about sFFT. Should read.

  * A feasible method for optimization with orthogonality constraints
    Wen, Yin


# Form
---

## Paper title
## Paper authors

#### Summary
(A 2-4 sentence summary of the paper)
Background / Context: Sentence on the setting of the paper, broad placement in field, large societal reason for the paper.
Motivation / Problem: The one sentence summary of the problem this is tackling and why it is important.
Method: How they solve the problem (build a system? algorithm? study?)
Results: Whats the speedup, the outcome, the takeaway.
Future: This is for you to thoughtfully extend or engage the work and what it means.

#### Strengths
  * List strengths of the paper here
  * In a list format

#### Weaknesses
  * List weaknesses of the paper here
  * In a list format

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?


Hot takes:
personal interest: x/10
paper quality / novelty: x/10

# DSP Theory
<!-------------------------------------------------------------------------------->
## Simple and Practical Algorithm for Sparse Fourier Transform
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
personal interest: 8/10 \
paper quality / novelty: 9/10 \
This is a fundamental development in DSP algorithms and is well-presented


## [The Sparse Fourier Transform: Theory and Practice](https://haitham.ece.illinois.edu/Papers/thesis.pdf)
#### Haitham Hassanieh, 2016

<!-------------------------------------------------------------------------------->

# Compressive Sensing Theory

<!-------------------------------------------------------------------------------->

## Fast and Efficient Compressive Sensing using Structurally Random Matrices
#### Thong T. Do, Lu Gan, Nam H. Nguyen, and Trac D. Tran, 2011

#### Summary
Compressive sensing has changed the way we look at sampling data; instead of sampling our signal directly, we can first "scramble" the signal (project it into a basis which is "incoherent" with some fixed representation basis in which we expect our signal to be sparse) and - because we scrambled the signal - take fewer measurements. The best applications of compressive sensing involve the "scrambling" happening in the real world before the signal ever hits our sensor, but a lot of times this is infeasible. Unfortunately, to "scramble" the signal takes O(M*N) time, where 'M' is the number of samples we which to take. We expect M > log(N), so our "scrambling" transform is slower than an FFT (which takes O(N log(N)))! How can systems which sample the signal directly still benefit from the speedups that CS would seem to offer?

The authors show a way of pre-processing the signal so that an FFT, DCT, or similar transform will sufficiently "scramble" the signal, allowing the "scramble" transformation to happen as fast as the transform, typically O(N log(N)). The transform matrix for the associated transform needs to satisfy some conditions set out in III.A. The authors also provide a proof that their way of pre-processing the signal followed by a transform satisfying their conditions will be sufficiently "scrambled".

This work basically lets us turn any fast, orthonormal transform into an incoherent CS transformation.

#### Strengths
  * Core method is interesting; provides a way to convert lots of methods into fast compressive sensing.

#### Weaknesses
  * Results with the boat pictures are underwhelming. I wonder why that's the case. The compression ratio is nowhere what we'd expect from even JPEG, but the images look pretty awful. Maybe it's because there's not yet any entropy coding. However, using entropy coding probably doesn't make sense; with these types of sensing matrices, we expect the captured and transmitted data to have high entropy, so lossless compression won't help much, if any. (see section IV.A / figure 10 of "Image compression based on compressive sensing: End-to-end comparison with JPEG" for a further discussion on the compressability of vectors projected into a random basis.)

#### Additional comments
Note the key condition that F (the transform)'s entries ALL need to be O(1/sqrt(N)). This rules out having a super-sparse F. I'm interested in seeing what part of the proof hinges on this condition... probably a very critical part lol.

Maybe this paper will shed some light on whether or not its possible for me to construct the sort of sensing matrix I want. Major gut-check on that though... practically speaking, we always need to encode the DC offset of many transforms (for instance, DCT). (I don't think) we can get this offset in sub-linear time (but can't we? CS can reconstruct undersampled images with the correct DC offset).

#### What potential directions of future work remain (if any)?
I'm interested in using this with some sort of "progressive" transform (like sparse FFT).

I really wanted to design a super sparse 'F', but it looks like for SRM to work, 'F' needs to be dense.


#### Hot takes:
personal interest: 9/10 \
This method may prove to be a powerful tool for adapting a fast transform to compressive sensing; compressive sensing is very easy to generalize across types of data. \
paper quality / novelty: 9/10 \

<!-------------------------------------------------------------------------------->

## Learning Compressed Sensing

#### Yair Weiss, Hyung Sung Chang, William Freeman, 2007

#### Summary
A key finding of Compressive Sensing is that noiseless, sparse signals can be perfectly reconstructed after undersampling in a *random* basis; however, this goes against conventional wisdom that a basis determined by PCA might be best. Is a random basis really the best we can do for real-world signals with noise? The authors define a new component analysis called "Uncertain Component Analysis" (UCA) which "[tries] to maximize the number of datapoints that can be accurately recovered from their noisy projections" (section III).

The authors provide a method for calculating the UCA of a dataset as well as a comparison between UCA, PCA, and random sampling bases. UCA performs as well as random projects in noiseless experiments (outperforming PCA) but as well as PCA in noisy experiments (outperforming random).

#### Strengths
 * Presents a new tool (UCA) for analyzing the optimal basis of a signal
 * Ties UCA to existing theories
 * Includes rigorous mathematical discussion as well as more approachable intuitive explanations

#### Weaknesses
 * Limited discussion of experimental results
 * No comparison to other types of sensing matrices (but perhaps these didn't exist yet; structurally random matrices didn't appear til 2011).

#### Additional Comments
I'm surprised that this paper is not more cited.\
Not super relevant to what I'm doing; this seems to be more relevant on the decoder side... But could still be relevant in the sense that it's asking "what're the most important parts of the signal to capture?"

#### What Potential directions of future work remain (if any)?
Is capturing a signal in a basis determined by UCA always going to take O(MN) time, or can we combine this with Structurally Random Matrices or BPBD to speed things up?

#### Hot Takes
personal interest: 6/10\
This is a moderately math-heavy work that's more focused on the decoder side; still relevant though.\
paper quality / novelty: 8/10\
Good discussion of a novel technique related to PCA. Would've liked to see more experimental data / discussion; maybe I glossed over that stuff too much in my reading.

<!-------------------------------------------------------------------------------->

## The Simplest Measurement Matrix for Compressed Sensing of Natural Images

#### Zaixing HE, Takahiro OGAWA, and Miki HASEYAMA, 2010

#### Summary
In classical compressive sensing, the transform into the 'sensing' domain is done by a dense, random matrix via a matrix multiplication, which takes O(NM) time. Some work has been done to improve this bound (e.g. structural random matrices, which let us get it in O(N log(N))). The authors present a sensing matrix which is very sparse, so multiplication can be carried out in O(M) time.

The authors provide a method for constructing their sparse sensing matrix, which consists of binary "Permuted Block Diagonal" matrices; an example is given in figure 2. These matrices are surprisingly simple, but provide reasonably good performance, as shown in figures 3 and 4.

BPBD sensing matrices open up new performance optimization opportunities for compressive sensing devices, both at the sensor end and at the processing end.

#### Strengths
 * Key result can offer significant performance improvements for compressive sensing
 * Simple construction of key result

#### Weaknesses
 * Evaluation of matrix doesn't seem very fleshed out; would've liked to see more pictures, more test cases.
 * Scrambled Block Hadamard in figure 5 has a pretty different color than the other pictures; would've liked to see that commented on.
 * Would've liked more discussion on beta parameter and how coherence could be affecting the reconstructed SNR.

#### Additional Comments
Need to check which papers cite this one!!

#### Hot Takes:
personal interest: 9/10\
Having a special type of transform / sampling matrix that is very computationally efficient but only appropriate for compressive sensing is really interesting to me\
paper quality / novelty: 7/10\
Seems like a simple but useful and novel improvement. Eval section lacking.

<!-------------------------------------------------------------------------------->

## Random filters for Compressive Sampling and Reconstruction
#### Tropp, Wakin, et. al, 2006

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

<!-------------------------------------------------------------------------------->

## A Lecture on Compressive Sensing
#### Richard G. Baraniuk

#### Summary
This paper summarizes the key findings of compressive sensing at a bachelor's degree level. It's widely accepted that we need to sample a bandlimited signal at the Nyquist rate to fully reconstruct it, but compressive sensing gives us an even lower bound for signals which we expect to be K-sparse in some domain which we call the "representation domain": we just need O(K log(N / K)) samples in a domain which is *incoherent* with the "representation domain". Surprisingly, a basis of vectors selected from random gaussian variables works optimally for sampling signals which are K-sparse in an arbitrary domain (for signals K-sparse in other, fixed domains, we can sometimes outperform the random basis, but the amount to which we can outperform it has a lower bound).

From this undersampled signal in an *incoherent domain*, we can use a non-linear optimizer to reconstruct the original signal in the *representation domain*, then we can just transform it back into the time or spatial domain. To do this, our optimizer finds the sparsest signal which "fits the evidence" - that is, which fits the measurements from the *incoherent domain*. In practice, we can't find the sparsest signal - this is an NP-hard problem - instead we minimize the l1-norm of the reconstructed signal as a proxy for sparsity. (comment: in some other problems like image reconstruction, minimizing a different cost like Total Variation (TV) in the spatial domain may yield better results).

Compressive sensing as an intellectual framework gives us ways to innovate in how data is collected and how data is reconstructed from incomplete samples. It can be used to reconsider every part of a data collection pipeline, including the sensors themselves, analog conversion circuitry, digital preprocessing of captured data, compression of captured data, transmission of captured data, and reconstruction of compressed signals.

#### Additional Comments
In the ideal application of compressive sensing, the signal is sensed in an *incoherent domain*. In the one-pixel camera, for instance, the signal is converted to an *incoherent domain* essentially by optical computing, which can perform the transformation much faster than a computer could. In cases where this is difficult or impossible due to the physical nature of the signal being sampled or the budget of the project (no $$ for custom circuitry), there could also be some promise in doing this computationally. Indeed, there will be many works that look at quick computational methods for converting into an incoherent domain.

<!-------------------------------------------------------------------------------->
## An Introduction to Compressive Sampling

#### Summary
This excellent intro article covers most of the same ground as the Baraniuk lecture, however, this one is more rigorous and slightly harder to approach.

<!-------------------------------------------------------------------------------->
## Robust Uncertainty Principles: Exact Signal Reconstruction from Highly Incomplete Frequency Information
#### Emmanuel Candès and Justin Romberg

#### Summary
A lot of times, we're interested in a signal that's sparse (or more generally, has a small norm), but we can't observe it directly; instead, we only have sparse samples in the frequency domain (as in the motivating example of tomography, where a subset of fourier coefficients can be observed). Existing methods make naive guesses about the values of the missing Fourier coefficients, leading to reconstructions with tons of artifacts.

Can we still reconstruct the signal even though we fewer samples than the Nyquist rate?

The authors solve this problem by posing the reconstruction as a Linear Programming problem; to reconstruct a sufficiently sparse signal from a sparse set of fourier coefficients, you just need to find the signal with minimum l-1 norm that fits the Fourier coefficients. Of course, the reconstruction doesn't always succeed; the authors provide a bound for which the reconstruction will be correct with overwhelming (1 - O(1/(N^M)) probability.

The majority of the paper consists of a proof that the l1-norm based reconstruction method is exact given certain bounds. The authors also do some numerical experiments showing the dropoff in accuracy of the reconstruction for different levels of sparsity.

In section 6.3, "Extensions", the authors discuss how they're able to restore the 2-d "phantom" images which are NOT sparse in the spatial domain, but do have a small "total-variation" norm because they're composed of a bunch of step-function like ellipses. They strongly hint at general compressive sensing as a future direction by describing that this method can possibly be generalized to domains other than the spike and fourier domains.


#### What potential directions of future work remain (if any)?
Future directions are fulfilled by the compressive sensing paper, I guess.

#### Hot takes:
personal interest: 7/10 \
The math in this one is quite a bit above my head. Perhaps if I understood it, it would help me extend this work in more basic ways.

paper quality / novelty: 10/10 \
Striking insight that lays the groundwork for compressive sensing.

<!-------------------------------------------------------------------------------->

## Sparsity and incoherence in compressive sampling

<!-------------------------------------------------------------------------------->

# Math

<!-------------------------------------------------------------------------------->

## Sparse orthogonal matrices
#### Cheon, Hwang, ... Song

## A Further Look Into Combinatorial Orthogonality

<!-------------------------------------------------------------------------------->

# Hardware Design

<!-------------------------------------------------------------------------------->

## Design and Analysis of a Hardware-Efficient Compressed Sensing Architecture for Data Compression in Wireless Sensors

<!-------------------------------------------------------------------------------->

## Compressive Sensing on a CMOS Separable-Transform Image Sensor

<!-------------------------------------------------------------------------------->
# Compressive Sensing Applications

<!-------------------------------------------------------------------------------->
## Block Compressed Sensing of Natural Images
#### Lu Gan, 2007

#### Summary
Transform coding - where data is encoded in a different domain (e.g. wavelet) than it was sampled (e.g. temporal/spatial) - has achieved a lot of success in data compression; these transforms usually expose sparsity which then can be very efficiently losslessly coded. A lot of times, this transform needs to be computed in a node with limited computational power, which can be infeasible. **Compressive Sensing** is a data representation paradigm where a signal can be undersampled in a domain Φ provided that the signal is sufficiently sparse in another domain Ψ and that Φ and Ψ satisfy certain other conditions. One of the promises of Compressive Sensing is the reduction of computational burden on sensor nodes, but for very long signals, storing / calculating Φ is impractical.

Using image compression as an example problem, the authors shrink Φ by splitting the image up into blocks (this paper found that 32x32 is the optimal size). They also introduce a new reconstruction algorithm which recovers each block by first doing MMSE linear reconstruction, then using Wiener filtering to reduce blocking artifacts and hard thresholding to reduce gaussian noise, both in the Lapped Transform domain. These techniques are on par or modestly better than earlier techniques in "Signal Recovery from Random Projections" (Candes, Romberg, 2006) while taking much less computational in both the encoder and decoder.

This paper is one of the earliest practical applications of Compressive Sensing to image compression. While the results are underwhelimg, there is a lot of improvement that can still be made, as this is an exploratory work.

#### Strengths
 * First paper to use compressive sensing for this application

#### Weaknesses
 * No justification of MMSE for reconstruction instead of L1-norm
 * No justification of use of Weiner filter instead of other filter
 * Tested on small number of images; only fully reconstructed image shown is Mondrian, which has little detail. Makes me think the author is trying to hide bad results.
 * Lackluster results compared to "Signal Recovery from Random Projections" (Candes, Romberg, 2006)
 * Results presented in hard-to-read table format

#### Additional comments
The connection between the proposed signal reconstruction method using MMSE and the classical Compressive Sensing problem is tenuous and difficult to understand.

Moreover, this method doesn't deliver at all on the promise of compressive sensing requiring less power than traditional transform methods. An FFT or FWT is still much faster than a multiplication by Φ. The authors don't address this point at all.

#### Hot Takes:
personal interest: 9/10\
paper quality / novelty: 4/10 \
This paper is widely cited, but it's an obvious application of a new (at the time) method to a problem with already-good solutions with very lackluster results.

<!-------------------------------------------------------------------------------->
## Energy-Efficient Image Compressive Transmission for Wireless Camera Networks

#### Yong Wang, Dianhong Wang, Xufan Zhang, Jun Chen, and Yamin Li (2016)

#### Summary
The authors make a wireless camera network system which uses a number of techniques to reduce the amount of power consumed by the nodes while still maintaining image quality.

#### Additional comments
In section IV.C of their paper, these folks get very close to what I'm proposing to do: "The quality of recovered images and energy consumption are two conflicting effects... using a higher value of MR leads to more energy [consumed due to computation] and bandwidth consumption yet causes better image quality". The key difference is that they don't look at compression schemes which trade off

<!-------------------------------------------------------------------------------->
## Optimal Compression and Transmission Rate Control for Node-Lifetime Maximization

#### Sheeraz A. Alvi, Xiangyun Zhou, and Salman Durrani (2018)

#### Summary


<!-------------------------------------------------------------------------------->
## Image Compression Based on Compressive Sensing: End-to-End Comparison with JPEG

<!-------------------------------------------------------------------------------->
## Adaptive Block Compressive Sensing: Toward a Real-Time and Low-Complexity Implementation

<!-------------------------------------------------------------------------------->
## A new wavelet based efficient image compression algorithm using compressive sensing

#### Muhammad Ali Qureshi, M. Deriche

#### Summary
A key insight of transform-based coding is that - for natural signals - it often groups most of the signal's energy in a few coefficients. The DWT of images is a great example of this: the low-pass parts (top left corner) of the transformed signal are dense, but the higher pass parts are very sparse. Although it has impressive theoretical performance, compressive sensing dispenses with this useful insight, resulting in samples where the signal's energy is evenly distributed over the samples. This may result in less-than-optimal compression performance.

The authors re-introduce the sparsity introduced to images by a DWT by first performing a DWT before converting to an incoherent domain, THEN performing the typical compressive sensing step of converting to an incoherent domain.

The authors compare the reconstructed quality via Peak Signal-to-Noise Ratio (PSNR) at varying Measurement ratios (MR) of their signal.

#### Strengths
 * Excellent eval section. Their method is applied to many different images.
 * Interesting insight.

#### Weaknesses
 * Would've liked to see eval against
 * Wonder about fundamental soundness. See discussion.

#### Additional Comments
Misses the point of CS? why not just leave in wavelet domain. We're already there. It's already K-sparse, why change to CS where we require O(K * log(N/K)) instead of just K? Maybe because it keeps us from having to encode the LOCATIONS of the K nonzero elements. Maybe need to read more to see.

<!-------------------------------------------------------------------------------->
## Perceptual compressive sensing for image signals

<!-------------------------------------------------------------------------------->
## Compressed Sensing: A Simple Deterministic Measurement Matrix and a Fast Recovery Algorithm

#### Andrianiaina Ravelomanantsoa, Student Member, IEEE, Hassan Rabah, Senior Member, IEEE, and Amar Rouane, 2015

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

#### What potential directions of future work remain (if any)?
Would like to see this evaluated on more types of signals.

#### Hot Takes:
personal interest: 8.5/10\
Pretty "white-bread" impl of existing research on a real system, but it's a system that's in my wheelhouse.\
paper quality / novelty: 7/10\
Took theory and put it in hardware. Eval was adequate, could've been stellar.

<!-------------------------------------------------------------------------------->
## Energy-Efficient Image Compressive Transmission for Wireless Camera Networks

#### Yong Wang, Dianhong Wang, Xufan Zhang, Jun Chen, and Yamin Li, 2016

#### Summary
Wireless camera nodes capture an amount of data that's far too large to send raw over a wireless network. Widely-used video compression techniques weren't designed with this sort of application in mind. They're power-hungry (our nodes don't have much power), they're memory-hungry, and they're not robust to packet loss (wireless mesh networks may drop a lot of packets). The authors introduce a compressive-sensing based video compression scheme and use it to construct a wireless camera node.

The proposed compression scheme first uses an online background classifier to distinguish between ROI and non-ROI tiles (Section IV.A); non-ROI tiles are encoded less frequently and with less precision. Next, it takes a block-based Haar Wavelet Transform and compressively samples the Haar Coefficients, using the sparsity of the Haar transform to dictate the number of samples to take (Section IV.B). The compression quality is modulated depending on the amount of remaining power; as a node's battery drains, its image quality will get progressively worse (Section IV.C).

The authors construct a sensor node with an Application level ARM processor running Linux, Zigbee and WiFi radios, and a 1.3Mp grayscale camera. They show their system recording video at different packet loss rates.

#### Strengths
 * They identify a few key places where a naive wireless camera node works too hard.
 * They build and test on real hardware
 * They develop a working end-to-end system that uses their technique (Section VI & Figure 9)

#### Weaknesses
 * Transform into Haar Wavelet Domain and THEN into CS domain only *barely* makes sense. Some justifying discussion would be good to know that these folks know what they're doing. Yeah, I know that putting it into the Haar Domain on the edge sensor gives them some idea of how many samples they need to take. And I know that
 * Their heuristic for trading off between power consumption and image quality could have been much more sophisticated and taken into consideration radio power consumption (which I assume varies with link quality).
 * Hardware platform is very high power

#### Additional Comments
It seems like the use of compressive sensing here is just as a way to modulate compression quality and provide some robustness to packet loss. I think there could be other, possibly better ways to achieve these goals... Maybe fountain codes? The conversion to the compressive domain AFTER taking the Haar Transform seems unnecessary.

Also, their quip at the start of the paper that JPEG is too power intensive doesn't make much sense. The scheme they have put together is much more energy intensive than JPEG.

Section IV.C disappoints; they could have also modulated depending on the power consumption of the radio over time (I assume that a weak link will require more power to send, depending on how channel state the protocol keeps track of).

#### Hot Takes:
Personal interest: 8/10\
This paper is very very close to what I plan to do, except they have more innovation on the ROI side than I would plan to do.\
Paper quality / novelty: 7/10\
Paper seems super novel to me, but it leaves a lot to be desired. See "additional comments".

<!-------------------------------------------------------------------------------->
## Xufan Zhang, Yong Wang, Dianhong Wang, Yamin Li, 2017
Note: this is a sequel to "Energy-Efficient Image Compressive Transmission for Wireless Camera Networks" by the same authors. The two papers are almost identical. This one was submitted about 1 year after the previous one.

#### Summary
This paper is substantially similar to "Energy-Efficient Image Compressive Transmission for Wireless Camera Networks" by the same authors. As far as I can tell, there are only a few differences:
 1. They add an elaborate way of re-arranging the Haar coefficients before applying the sensing matrix; this results in a shorter sampling matrix.
 2. Removal of discussion about ROI
 3. Additional experiments on different images

#### Strengths
 *

#### Weaknesses
 * Their method for rearranging the HWT coefficients is not explained clearly. An opaque explanation is made worse by very bad typesetting (Section 3.1).

# Compressive Sensing Decoders

## ReconNet: Non-Iterative Reconstruction of Images from Compressively Sensed Measurements
#### Kuldeep Kulkarni Suhas Lohit, Pavan Turaga, Ronan Kerviche, and Amit Ashok, 2016

#### Summary
Compressive sensing requires reconstruction of a signal which has been undersampled in a random domain. In the classical formulation of CS, this can be achieved precisely as long as the signals satisfy certain requirements, but these requirements are often only loosely met in practice, leading to reconstructions that take a prohibitively long time and yield unsatisfying results. The authors present a new CS reconstruction strategy.

In this work, the authors reconstruct images that are undersampled in a random domain. They do this in a block-wise fashion, first breaking each image up into a 33x33 block. They use a 6-layer CNN which they call "ReconNet" to reconstruct the image, followed by an off-the-shelf denoising filter. The size of the network's first layer depends on the sampling rate, so the network needs to be re-trained for each sampling rate. The sampling matrix is fixed and the network is trained on blocks taken from a relatively small set of images. They evaluate their system against several other reconstruction methods at various undersampling rates in simulation AND by photos taken with a real DMD-based single-pixel camera. At high undersampling rates, ReconNet outperforms other methods consistently.


#### Additional Comments
I'm interested in knowing how much implicit information about the world is encoded in the network. Does the network learn what a letter 'A' looks like and so is more likely to decode that? I strongly suspect that this is NOT the case (due to the small size of the training set and block-based image segmentation), but I would like to read further into the paper to know for sure.

ALSO: this paper is a GREAT SOURCE for references about CS decoders.

#### Hot Takes
personal interest: 7/10\
I'm less interested in CS decompression than CS compression - especially if it's about lowering the computational burden at the reconstruction side. However, what's possible in reconstruction determines what's possible at the sampling end, so I still need to keep tabs on this.

paper quality / novelty: 8/10\
Very vanilla usage of a small CNN. Seems like an instance of playing "neural network" mad libs with a well-established problem, but the authors have written the paper well; explanation of the network is well done and evaluation is pretty complete.


  * Compressive sensing based image compression-encryption using Novel 1D-Chaotic map


  * ADVANCES IN SPARSE SIGNAL ANALYSIS WITH  APPLICATIONS TO BLIND SOURCE SEPARATION AND  EEG/MEG SIGNAL PROCESSING
    PhD thesis by Nasser Mourad

  * The PhD student from Katabi's sFFT wrote a whole thesis about sFFT. Should read.

  * A feasible method for optimization with orthogonality constraints
    Wen, Yin

## Design and Analysis of a Hardware-Efficient Compressed Sensing Architecture for Data Compression in Wireless Sensors

## A Fast Hadamard Transform for Signals with Sub-linear Sparsity in the Transform Domain
#### Robin Scheibler Saeid Haghighatshoar, Martin Vetterli, 2013

#### Summary
Transforming signals into a different domain is a "bread-and-butter" task in DSP. Arbitrary transforms take O(N^2) time, but we can get fourier (and related) transforms in O(N log(N)) time. Recent methods have been developed which lower this bound for fourier transform as long as the signal is K-sparse in the Fourier domain. The authors extend this notion to the Walsh-Hadamard Transform, another transform widely used in frequency analysis.

The details of the algorithm are not easy to follow in this paper, but figures 2 and 3 explain a lot. It seems like they've taken some inspiration from coding theory and have sort of reduced the problem to using probability to solve a combinatorial problem.

It's unclear to me whether the signal NEEDS to be K-sparse in the WHT domain, or if the algorithm will recover something that's close to K-sparsity (like the sFFT). The authors also remark that their method is very unstable in the presence of noise (even floating-point noise was enough to kill their algorithm in some cases!)

#### Strengths
 *

#### Weaknesses
 * Meaning of parameter "beta" is unclear on a quick skim
 * Can't get much info about how important the sparsity is on a quick skim

#### Additional Comments
Like I said, I'm not sure if this method only works for signals that are exactly K-sparse (all other components need to be PRECISELY zero). If that is the case, then it seems like this would be useless for practical purposes (still could be theoretically useful though).

#### Hot Takes
Personal interest: 6/10\
If this paper does what I think it does, then it's very interesting, however I'm not sure if it does AND I'm not sure how it scales to modestly sparse signals with smaller length.\
Paper Quality / Novelty: 7.5/10\
Not really sure how to judge this. Feels like a riff on the sFFT paper, but the connection to coding theory is pretty cool.\

# Some related research ideas I'd like to try

#### Allowing dropped data samples
Intermittent computing often has a high probability of failure to deliver data. As a rhyme to "fountain codes" where dropped packets are ok because we send way more data than we need by generating redundancy, if we plan to send N incoherent samples of a length-N signal but only O(M * log(N/M)) of them arrive (due to power failure, link failure, MAC failure), then we have a good probability of recovering the original signal. If the incoherent basis is random, then presumably it doesn't matter which ones we drop.

#### Undersampling camera
Can we selectively turn pixels off in a camera instead of using a DMD mirror to get some of the benefits of the "single pixel camera" trick (i.e. power reduction) without the wackiness / high power consumption of a DMD mirror / TFT display covering the sensor? Yeah, I know the point of the single-pixel camera is "many nice (THz/IR sensitive, super good SNR, fast, etc etc) pixel expensive, one nice pixel cheap", but could we flip that script to energize only O(N * log(N/M)) pixels in total instead of O(N) pixels and still get a good picture?

Could probably use an off-the-shelf image sensor


# Form

## Paper title
#### Paper authors

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

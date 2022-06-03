# DSP Theory
 - [[Simple and Practical Algorithm for Sparse Fourier Transform]]
 - [The Sparse Fourier Transform: Theory and Practice](https://haitham.ece.illinois.edu/Papers/thesis.pdf)

# Compressive Sensing Theory
 - [[Current-Driven Magnetization Reversal and Spin-Wave Excitations in Co Cu Co Pillars]]
 - [[Learning Compressed Sensing]]
This is a moderately math-heavy work that's more focused on the decoder side; still relevant though.
 - [[The Simplest Measurement Matrix for Compressed Sensing of Natural Images]]
Having a special type of transform / sampling matrix that is very computationally efficient but only appropriate for compressive sensing is really interesting to me
 - [[Random filters for Compressive Sampling and Reconstruction]]
 - [[An Introduction to Compressive Sampling]]
 - [[A Lecture on Compressive Sensing]]
 - [[Robust Uncertainty Principles Exact Signal Reconstruction from Highly Incomplete Frequency Information]]
The math in this one is quite a bit above my head. Perhaps if I understood it, it would help me extend this work in more basic ways. This paper lays the groundwork for compressive sensing.
 - [[Sparsity and incoherence in compressive sampling]]

# Math
 - [[unfiled/Sparse Orthogonal Matrices]]
Cheon, Hwang, ... Song
 - [[Want to Read/A Further Look Into Combinatorial Orthogonality]]

# Hardware Design
 - [[Want to Read/Design and Analysis of a Hardware-Efficient Compressed Sensing Architecture for Data Compression in Wireless Sensors]]
 - [[Want to Read/Compressive Sensing on a CMOS Separable-Transform Image Sensor]]

# Compressive Sensing Applications
 - [[Block Compressed Sensing of Natural Images]]
 - [[Energy-Efficient Image Compressive Transmission for Wireless Camera Networks]]
 - [[Want to Read/Optimal Compression and Transmission Rate Control for Node-Lifetime Maximization]]
 - [[Image Compression Based on Compressive Sensing End-to-End Comparison with JPEG]]
 - [[Want to Read/Adaptive Block Compressive Sensing: Toward a Real-Time and Low-Complexity Implementation]]
 - [[A new wavelet based efficient image compression algorithm using compressive sensing]]
 - [[Want to Read/Perceptual compressive sensing for image signals]]
 - [[Compressed Sensing A Simple Deterministic Measurement Matrix and a Fast Recovery Algorithm]]
Pretty "white-bread" impl of existing research on a real system, but it's a system that's in my wheelhouse.
 - [[Energy-Efficient Image Compressive Transmission for Wireless Camera Networks]]
This paper is very very close to what I plan to do, except they have more innovation on the ROI side than I would plan to do.
<!-------------------------------------------------------------------------------->


<!-------------------------------------------------------------------------------->

# Compressive Sensing Decoders
 - [[ReconNet Non-Iterative Reconstruction of Images from Compressively Sensed Measurements]]
- Compressive sensing based image compression-encryption using Novel 1D-Chaotic map
 - ADVANCES IN SPARSE SIGNAL ANALYSIS WITH  APPLICATIONS TO BLIND SOURCE SEPARATION AND  EEG/MEG SIGNAL PROCESSING
    PhD thesis by Nasser Mourad
 - The PhD student from Katabi's sFFT wrote a whole thesis about sFFT. Should read.
 - A feasible method for optimization with orthogonality constraints
    Wen, Yin
 - Design and Analysis of a Hardware-Efficient Compressed Sensing Architecture for Data Compression in Wireless Sensors
 - [[A Fast Hadamard Transform for Signals with Sub-linear Sparsity in the Transform Domain]]


# Some related research ideas I'd like to try

#### Allowing dropped data samples
Intermittent computing often has a high probability of failure to deliver data. As a rhyme to "fountain codes" where dropped packets are ok because we send way more data than we need by generating redundancy, if we plan to send N incoherent samples of a length-N signal but only O(M * log(N/M)) of them arrive (due to power failure, link failure, MAC failure), then we have a good probability of recovering the original signal. If the incoherent basis is random, then presumably it doesn't matter which ones we drop.

#### Undersampling camera
Can we selectively turn pixels off in a camera instead of using a DMD mirror to get some of the benefits of the "single pixel camera" trick (i.e. power reduction) without the wackiness / high power consumption of a DMD mirror / TFT display covering the sensor? Yeah, I know the point of the single-pixel camera is "many nice (THz/IR sensitive, super good SNR, fast, etc etc) pixel expensive, one nice pixel cheap", but could we flip that script to energize only O(N * log(N/M)) pixels in total instead of O(N) pixels and still get a good picture?

Could probably use an off-the-shelf image sensor
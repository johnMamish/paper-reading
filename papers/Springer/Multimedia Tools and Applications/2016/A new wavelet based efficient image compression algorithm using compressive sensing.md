## A new wavelet based efficient image compression algorithm using compressive sensing

#### [[authors/Muhammad Ali Qureshi]] and M. Deriche, 2016

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

Keywords: [[compressive-sensing]] [[compression]] [[keywords/wavelets]] [[dsp]] [[keywords/sparse-representation]]

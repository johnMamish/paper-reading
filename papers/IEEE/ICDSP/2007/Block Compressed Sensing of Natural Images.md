## Block Compressed Sensing of Natural Images
#### [[Lu Gan]], 2007
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

This paper is widely cited, but it's an obvious application of a new (at the time) method to a problem with already-good solutions with very lackluster results.

Keywords: [[compressive-sensing]]
Tags: [[highly-cited]]


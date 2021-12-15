## The Simplest Measurement Matrix for Compressed Sensing of Natural Images

#### [[authors/Zaixing He]], [[authors/Takahiro Ogawa]], and [[authors/Miki Haseyama]], 2010

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
Measurement matrix is really very very simple... just like they say.

Keywords: [[compressive-sensing]] [[keywords/hardware-implementation]] [[keywords/sensing-matrix]]

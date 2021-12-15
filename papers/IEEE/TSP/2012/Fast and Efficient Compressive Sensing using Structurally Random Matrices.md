## Fast and Efficient Compressive Sensing using Structurally Random Matrices
#### [[authors/Thong T Do]], [[Lu Gan]], [[authors/Nam H Nguyen]], and [[authors/Trac D Tran]], 2012

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

Keywords: [[compressive-sensing]] [[keywords/sparse-reconstruction]]

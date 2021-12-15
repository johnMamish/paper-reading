## A Fast Hadamard Transform for Signals with Sub-linear Sparsity in the Transform Domain
#### [[authors/Robin Scheibler]], [[authors/Saeid Haghighatshoar]], [[authors/Martin Vetterli]], 2013

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

If this paper does what I think it does, then it's very interesting, however I'm not sure if it does AND I'm not sure how it scales to modestly sparse signals with smaller length.

Keywords: [[compressive-sensing]] [[dsp]] [[keywords/hadamard-transform]] [[sparse-fourier-transform]]

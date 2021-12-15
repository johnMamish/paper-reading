## A Lecture on Compressive Sensing
#### [[Richard Baraniuk]], 2007

#### Summary
This paper summarizes the key findings of compressive sensing at a bachelor's degree level. It's widely accepted that we need to sample a bandlimited signal at the Nyquist rate to fully reconstruct it, but compressive sensing gives us an even lower bound for signals which we expect to be K-sparse in some domain which we call the "representation domain": we just need O(K log(N / K)) samples in a domain which is *incoherent* with the "representation domain". Surprisingly, a basis of vectors selected from random gaussian variables works optimally for sampling signals which are K-sparse in an arbitrary domain (for signals K-sparse in other, fixed domains, we can sometimes outperform the random basis, but the amount to which we can outperform it has a lower bound).

From this undersampled signal in an *incoherent domain*, we can use a non-linear optimizer to reconstruct the original signal in the *representation domain*, then we can just transform it back into the time or spatial domain. To do this, our optimizer finds the sparsest signal which "fits the evidence" - that is, which fits the measurements from the *incoherent domain*. In practice, we can't find the sparsest signal - this is an NP-hard problem - instead we minimize the l1-norm of the reconstructed signal as a proxy for sparsity. (comment: in some other problems like image reconstruction, minimizing a different cost like Total Variation (TV) in the spatial domain may yield better results).

Compressive sensing as an intellectual framework gives us ways to innovate in how data is collected and how data is reconstructed from incomplete samples. It can be used to reconsider every part of a data collection pipeline, including the sensors themselves, analog conversion circuitry, digital preprocessing of captured data, compression of captured data, transmission of captured data, and reconstruction of compressed signals.

#### Additional Comments
In the ideal application of compressive sensing, the signal is sensed in an *incoherent domain*. In the one-pixel camera, for instance, the signal is converted to an *incoherent domain* essentially by optical computing, which can perform the transformation much faster than a computer could. In cases where this is difficult or impossible due to the physical nature of the signal being sampled or the budget of the project (no \$\$ for custom circuitry), there could also be some promise in doing this computationally. Indeed, there will be many works that look at quick computational methods for converting into an incoherent domain

Keywords: [[compressive-sensing]] [[keywords/dsp]]
Tags: [[tags/foundational]]
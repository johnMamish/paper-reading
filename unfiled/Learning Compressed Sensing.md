## Learning Compressed Sensing

#### [[authors/Yair Weiss]], [[authors/Hyung Sung Chang]], [[authors/William Freeman]], 2007

#### Summary
A key finding of Compressive Sensing is that noiseless, sparse signals can be perfectly reconstructed after undersampling in a *random* basis; however, this goes against conventional wisdom that a basis determined by PCA might be best. Is a random basis really the best we can do for real-world signals with noise? The authors define a new component analysis called "Uncertain Component Analysis" (UCA) which "\[tries\] to maximize the number of datapoints that can be accurately recovered from their noisy projections" (section III).

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

Keywords: [[compressive-sensing]] [[keywords/pca]] [[sparse-reconstruction]]

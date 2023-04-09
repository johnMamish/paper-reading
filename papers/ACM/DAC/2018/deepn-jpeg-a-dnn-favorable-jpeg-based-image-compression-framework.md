 ## DeepN-JPEG: A Deep Neural Network Favorable JPEG-based  Image Compression Framework
#### Liu, Liu, Wen, Jiang, Wang, Xu, Quan, 2018 (DAC18)
#### Summary
Much of the data collected by edge sensors is destined for consumption by DNN-based classifiers, but is compressed using lossy heuristics designed for the human senses. This paper aims to tailor JPEG compression to DNNs, introducing error that will be impreceptable to DNNs instead of impreceptable to humans.

The authors use the unmodified JPEG algorithm which throws away information in some frequency bands more than others, but with quantization tables that are tailored specficially for each network. The authors generate tailored quantization tables NOT by looking at the network itself, but instead by looking at the data the network was trained on. They look at the statistical distribution of the magnitude of the frequency components of uncompressed images in the training data. The components with the largest standard deviation are judges to be most important to the network's preception and therefore get the smallest quantization factors (Figure 4).

The authors find that images compressed with their quantization tables are 3.5x smaller than images compressed with standard quantization tables with NO loss of classification accuracy (Figure 8). Compressing by a similar factor using standard Q-tables gives a drop of a few percent in accuracy.

#### Strengths
  - Novel idea that exploits something obvious
  - Very backwards-compatible
  - Major gains
  - Computationally cheap to search for tables

#### Weaknesses
  - Somewhat underwhelming results (Figure 8)
  - Basic idea is good, but the technique they use to exploit it is a very sloppy heuristic

#### Additional comments
The authors have a fundamentally very good idea, but it seems like they implement and present the easiest proof-of-concept possible. I imagine that there is lush unexplored territory for much more sophisticated and theoretically grounded related techniques. For instance...
 - I'm very interested in seeing what would happen if the NETWORK itself was probed instead of the training data. Maybe expose the network to the various DCT basis functions and look at the magnitude of the response from the first few layers?
 - What if you trained the network jointly with something that would automatically select an ideal basis for representation?

#### What potential directions of future work remain (if any)?
See "additional comments"

#### Citations
Need to find some papers which cite this one.

Keywords: [[compression]], [[deep-learning]], [[low-power]]
Tags: [[favorite]]
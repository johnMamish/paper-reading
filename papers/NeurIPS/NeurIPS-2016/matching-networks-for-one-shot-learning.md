## Matching Networks for One-Shot Learning
#### [[authors/Oriol Vinyals]], [[authors/Charles Blundell]], [[authors/Timothy Lillicrap]], [[authors/Koray Kavukcuoglu]], [[authors/Daan Wierstra]], 2016
#### Summary
A major limitation of neural networks is their need for vast amounts of training data when new classes must be learned. The authors propose a new neural network architecture which they call Matching Networks. Instead of learning a mapping from input vectors to output vectors, Matching Networks learn a mapping of input vectors to classifiers. They do this by using what they call an "attention mechanism"; AFAICT, this classifier determines how similar a new input is to previously seen classes. They also introduce a new training method for Matching Networks.

The authors find that their system outperforms all other methods for one-shot learning across a variety of workloads. They also introduce several new datasets for work on one-shot learning.

#### Strengths

#### Weaknesse

#### Additional comments
Honestly I'm kind of out of my depth with this paper. I barely understand the problem it solves, and I have even less clarity on how it solves it.

#### What potential directions of future work remain (if any)?

#### Citations
 - "Memory Networks" by Weston, Chopra, and Bordes (ICLR, 2014) seems to be particularly foundational for this paper

Keywords: [[deep-learning]]
Tags: [[highly-cited]]
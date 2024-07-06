#### Eugene V. Solodovnik, Shengyi Liu, and Roger A. Dougal, 2002
#### Summary
Solar Panels deliver the most energy when biased at a particular I/V point. In practice, this is done by changing the duty cycle of a switching regulator, however, choosing the regulator duty cycle u(t) is a difficult optimization problem; the optimal u(t) depends strongly on weather and solar cell conditions and tracking the optimal u(t) is computationally expensive.

The authors pose this as a nonlinear control problem and mathematically derive an optimal control policy which also minimizes the dimensionality of the state space so that controller complexity is minimized. They ensure the stability of their approach. They show the viability of their control policy using a simulation platform.

This work seems to be foundational in the field of energy harvesting. I would be interested in further discussion of regulator modes and what output voltage ranges are permissible. I'd like to read the work more closely and see if they assume a certain regulator operating mode.

#### Strengths
  - Mathematical rigor
  - High impact problem domain

#### Weaknesses
  - Only tested in simulaton
  - I think that some practical switching regulator issues might've been glossed over, but maybe that's just because I didn't read close enough.

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[energy-harvesting]], [[keywords/power-converters]]
Tags: [[foundational]]
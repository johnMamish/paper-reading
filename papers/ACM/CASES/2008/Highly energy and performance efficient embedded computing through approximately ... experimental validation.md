## Highly energy and performance efficient embedded computing through approximately correct arithmetic A mathematical foundation and preliminary experimental validation
#### [[authors/Lakshmi Chakrapani]], [[authors/Kirthi Krishna Muntimadugu]], [[authors/Avinash Lingamneni]], [[authors/Jason George]], [[authors/Krishna Palem]], 2008
#### Summary
Many calculations are robust to small errors, however, arithmetic hardware often includes large amounts of timing slack; this makes error-free operation absolutely certain, but a lot of extra time is taken for many computations, increasing the energy consumption per calculation. This paper formalizes an earlier circuit-level technique for reducing the energy consumption of integer addition at the cost of introducing arithmetic errors. This technique works by introducing several voltage domains for different parts of the adder; MSbs are supplied with a higher voltage, taking more energy but decreasing propagation time. The authors mathematically formalize the notion of non-uniform propagation delays inside the adder and establish upper bounds for expected arithmetic error as a function of propagation delay.

To validate their technique, the authors use HSPICE and a bespoke C simulator to model a 16-bit ripple carry adder which has 4 seperate voltage domains. They show that the average magnitude of error at a given clock frequency or given energy is much lower for nonuniform voltage scaling than for uniform voltage scaling. They also process multimedia data (by taking its DFT and IDFT) to show that the non-uniform voltage scaling hardware far outperforms uniform voltage scaling at a fixed energy.

This method shows a lot of promise for ML applications (which are famously error tolerant), especially if the voltage can be dynamically scaled at runtime.

#### Strengths
  - The authors introduce a theoretical framework formalizing an existing design approach
  - Good eval section (I really liked the histograms in fig 7)

#### Weaknesses
  - Not a lot of detail given regarding HOW they went about evaluating their approach (no discussion of their "C based behaviorial simulator")

#### Additional comments
This paper introduces an idea that I pitched to Jie Gu in 2019. Too bad I was a decade late lol.

#### What potential directions of future work remain (if any)?
Application to low-power deep learning.

Could be interesting to try and characterize how error tolerant each operation of a DNN is. If we could say "this operation is very error resistant", we could choose specific operations to scale when evaluating a DNN.

Something I've always wondered - is there a way to do addition in "reverse"? Results propagate from the MSB to the LSB, so that half-baked results accumulate error in the LSBs instead of the MSBs.

#### Citations
Some comments about the citations
 - [[want to read/Probabilistic Arithmetic and Energy Efficient Embedded Signal Processing]] is an earlier version of this idea by the same authors. This paper may just be a re-hash/extension of [[IMPACT: IMPrecise adders for low-power Approximate CompuTing]], a similar idea by the same authors.
 - [[Low-Power Digital Signal Processing Using Approximate Adders]] is a widely-cited paper that uses this work as inspiration. IMO, their approach is less elegant but much easier to implement in practice.
 - [[Dynamic Knobs for Responsive Power-Aware Computing]] uses software-based approaches to achieve its goals, but could be adapted to use the hardware in this paper.

Keywords: [[approximate-computing]], [[low-power]], [[vlsi]], [[dsp]]
Tags: [[favorite]]
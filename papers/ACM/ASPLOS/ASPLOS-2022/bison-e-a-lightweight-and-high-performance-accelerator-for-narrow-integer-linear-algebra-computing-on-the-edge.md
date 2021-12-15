## BiSon-e: A Lightweight and High-Performance Accelerator for Narrow Integer Linear Algebra Computing on the Edge
## ???, 2022

#### Summary
Recent work in linear algebra has stirred interest in the use of lower-precision fixed-point data types; researchers are finding that classifiers working with 4- or even 1- bit integers can achieve good performance. Earlier work called "binary segmentation" [6] explores the idea of expressing several SIMD operations on very short numbers in terms of a single operation on a longer number, basically by concatenating the shorter numbers into a longer number (Sections 2.{1,2} and Figure 1 show how to do this for dot product and convolution). For example, this technique lets us "trick" a 64-bit ALU into adding 10 pairs of 5-bit numbers in parallel with a single 'add' operation. Unfortunately, pretty much every CPU today assumes that the minimum data size you'd want to work with is 8 bits, meaning that the bit-manipulations (shifting and masking) required to take advantage of this technique are prohibitively expensive.

To make "binary segmentation" computationally useful, the authors propose the addition of a very small piece of bit-manipulation hardware to a CPU's data path in front of the ALU (Figure 5). Because the bit operations in question are very simple, the added hardware is very small (figure 10). In cases where the operand bit-width is short, a speedup of many times can be achieved (Figures {7, 8, 9}).

I think a clear next direction for the authors is compiler support for BiSon-e and fabrication of a real chip.

#### Strengths
 * Breathes life back into an old technique; that's cool.
 * Harnesses computing power that is being wasted every time a computation that's less than the CPU's data width is carried out.
 * Hardware is *almost* built - full P&R
 * Technique is conceptually very simple
 * Technique is very simple in implementation
 * Technique has low implementation overhead

#### Weaknesses
 * Experimental evaluation only on 64-bit processors (I think?)
 * I'd expect much more modest improvement on 32-bit processors.

#### Hot takes:
Personal interest: 9/10\
A clever, simple, elegant, architecture innovation for low-power computing. I would have been very satisfied & proud working on this.\
Paper quality / novelty: 8.5/10\
This technique almost feels like a stop-gap as we move toward more and more specialized accelerators.

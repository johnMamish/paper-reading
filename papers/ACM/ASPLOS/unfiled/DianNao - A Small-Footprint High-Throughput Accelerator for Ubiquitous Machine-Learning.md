## DianNao: A Small-Footprint High-Throughput Accelerator for Ubiquitous Machine-Learning
#### Tianshi Chen, Zidong Du, Olivier Temam, et. Al, 2013
#### Summary
(At the time of writing), Deep learning applications are becoming ubiquitous, but CPUs, GPUs, and FPGAs are still being used to process DNNs; creating an ASIC for DNN evaluation would provide passive speed and energy benefits. Previous work has looked at doing this, but the focus is mostly on speeding up the computation itself, not on the memory accesses, which often take more energy than the computations.

To address this issue, the authors introduce DianNao, a DNN accelerator designed with a special focus on optimizing memory accesses. They achieve this by having separate memory access structures for layer input data, layer output data, and weights / biases. After fetching, each of these are held in seperate on-chip scratchpad memories. By keeping these in separate memories and by using manually managed scratchpads instead of caches, memory conflicts and memory circuit overhead respectively are significantly reduced. The actual computation takes place in a 3-stage pipeline. A number of other clever memory optimizations enable performance. The entire system is controlled by a simple assembly language which manages memory fetches. Figure 11 provides an excellent system overview. Importantly, they use 16-bit fixed point arithmetic for everything - they show that this provides ~5x area and energy savings over 32b FP with almost 0 penality on QoR (Fig 12, Table 1, Table 2).

The authors simulate their system in a 65nm process. It achieves a speed improvement of ~100x and an energy reduction of ~20x compared to a 128b SIMD processor.

#### Strengths
  - Good insight about the relative energy cost of memory accesses vs arithmetic
  - Very impressive engineering effort
  - Impressive results

#### Weaknesses
  - I'm skeptical that they might be strawmanning previous work. Did nobody else think to treat memory accesses in a DNN asic??
  - Comparison should have also been made against GPU and FPGA. Comparison against SIMD CPU feels unfair.
  - Would've loved to see a taped out chip
  - Would've liked to see discussion about performance inside an SoC.

#### Additional comments
If this is integrated into an SoC so it has to share a RAM bus with less deterministic components, how does that affect the careful dance of the scratchpad memory? I agree with the choice to remove cache circuitry and assume 100% accurate speculations, but the overhead that comes with the nondeterministic latency when you share a bus with the rest of an SoC might cause performance issues.

^^^^ Perhaps this was addressed in the paper, but I missed it.

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[deep-learning]], [[vlsi]], [[keywords/mobile-computing]], [[FPGA]]
Tags: [[foundational]], [[tags/best-paper-award]]
Read date: [[july]]
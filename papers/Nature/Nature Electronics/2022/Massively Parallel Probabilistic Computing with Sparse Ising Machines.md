## Massively Parallel Probabilistic Computing with Sparse Ising Machines
#### [[authors/Navid Anjum Aadit]], [[authors/Kerem Camsari]], et. al, 2022
#### Summary
NP problems are ubiquitious across many domains, but quickly become intractable as the problem size grows when executed on a traditional von neumann architecture. Ising Machines are an alternative model of computation rooted in statistical mechanics whereby a probabilistic system occupies different solution states with probability proportional to the exponent of the product of the state's cost and an "inverse temperature" variable. Just like a corresponding physical system, this system will tend to occupy lower energy states.

The authors of this paper implement a system on an FPGA which can exploit the inherent parallelism of this problem. By operating different parts of the system with different clock phases, they are able to update their system in parallel, avoiding oscillatory states that arise when updates are applied serially. In order for their parallel updating scheme to work, the connection graph between P-Bits must be colorable with few colors (5 in this paper), and therefore must be sparse. They introduce a method that sparsifies the problem graph at the expense of adding more nodes.

They experimentally demonstrate their FPGA-based system on 2 example problems - prime factorization and 3SAT. They show that their system is capable of executing ~5x more Ising evalutions (called flips) per nanosecond than an NVIDIA fermi GPU (Table 1). The show exact factorization of a 32-bit number (figure 3) and approximate solution of a SAT problem; as a SAT solver, their system outperforms state-of-the-art SAT systems.

This is promising and amazing work. I'm interested in seeing how dedicated hardware can improve on these results.

#### Strengths
  - Physical implementation of non-conventional computing architecture
  - Compares favorably with state-of-the-art methods in practice. Not just some wild, boffin-y experiment

#### Weaknesses
  - Phase difference mechanism poorly explained. I don't think it's strictly necessary
  - Discussion of problem setup limited

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?
I'm interested in seeing how this approach could be used in intermittent systems..... what problems can we pose as approximate NP problems?
	Scheduling?
	Data Compression?
	Networking?
	Energy rationing?
	Classification?

#### Citations

Keywords: [[keywords/FPGA]], [[keywords/architecture]]
Tags: 
## Manticore: Hardware-Accelerated RTL Simulation with StaticBulk-Synchronous Parallelism
#### Mahyar Emami, Sahand Kashani, James R. Larus, et. al, 2024
#### Summary
Simulation is one of the biggest time-sinks when designing digital logic - simulations can take hours or days. RTL simulations can be sped up through parallelization, but communication overhead in modern CPUs limits this speedup significantly. The authors introduce an accelerator system specifically designed for speeding up RTL acceleration as well as a compiler which converts testbenches into code that can run on their accelerator.

The authors observe that any computation performed by RTL in a single cycle (assuming no latches?) can be represented by a DAG. Their compiler analyzes the RTL to be simulated and constructs many disjoint DAGs (figure 1), each of which - provided the system state at cycle N - can be calculated independently to produce the system state at cycle N+1. Their manycore accelerator system - Manticore - can evaluate each of these dags independently on seperate cores, resulting in massive speedup. A key insight of this work is that - because of the regular structure of the computations - all inter-core communication can be done at compile time, making the design of each individual core much simpler. The cores are designed to be instantiated on an FPGA - each core's register file is massive (consists of 4 BRAMs) and cores are optimized to perform logic operations quickly.

The authors instantiate their accelerator on an Alveo U200 FPGA PCIe card, which uses a Virtex UltraScale+ FPGA. Due to the FPGA-tailored design of the accelerator cores, they are able to instantiate 225 cores, which run at ~500MHz. They compare Manticore's performance with Verilator's with Verilator running on different CPUs (Table 3). They find a speedup of ~1.5-4x over Verilator depending on the design being simulated. 

As the industry appetite for application-specific accelerators grows, this work will certainly be very appealing to semiconductor EDA companies.

#### Strengths
  - Basic insight - that inter-processor communication for RTL simulation can be performed at compile time - is great.
  - Incredible engineering effort. Both an accelerator and a compiler were designed and implemented.
  - Great outcome in a high-impact area.

#### Weaknesses
  - I'm skeptical that this system will work as-is for designs with multiple clock domains. Will be possible to extend to that, but I wish they'd mention it.
  - Also, what about designs using latches?

#### Additional comments


#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - Followup paper from same group: A 475 MHz Manycore FPGA Accelerator for RTL Simulation

Keywords:  [[cad]], [[FPGA]], [[keywords/accelerator]]
Tags: 
Read date: [[read date/2024/august]]
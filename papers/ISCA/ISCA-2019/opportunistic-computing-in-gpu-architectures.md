Hot takes:
personal interest: 3/10
paper quality: 7/10

GPUs already have an insane amount of memory bandwidth, and it's just going to get worse as they scale. If we can offload some simple GPU computations to memory, we can reduce memory bandwidth and latency. This technique is already working pretty well for CPUs.

The authors introduce 2 related techniques that - as far as I can tell - are compile-time but rely on a little bit of extra hardware. These techniques rely on the fact that modern GPUs often consist of a grid of interconnected cores and that one GPUs memory request might be routed to the LLC in another GPU. The authors statically identify "Earliest Meet Nodes" - the precise definition of which I didn't have time to figure out - which appear to be the place where computation on a certain memory element can most conveniently take place.
  1. "LLC (last-level-cache)-compute" In LLC-compute, the authors identify chains of instructions that can be effectively offloaded to computation circuitry in last-level caches, never making their way to the GPU itself. AFAICT, these chains are all identified statically at compile time (section 4.2). From a very high-level reading, it looks like they add a little bit of extra computation circuitry in LLCs, and the GPU can issue a "computation request" for a certain memory address instead of a load/operate/store sequence of instructions.
  2. "omnicompute" - they identify the GPU connected to an "earliest meet node" and leverage its spare cycles to perform the required compute-in-memory.
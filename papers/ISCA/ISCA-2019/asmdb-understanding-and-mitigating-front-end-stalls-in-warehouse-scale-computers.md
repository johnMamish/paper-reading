Application code size - especially in WSCs - has grown drastically, and continues to balloon (one major contributing factor is aggressive inlining (section 4.2)). In large executables, "hot" code - code that is used a lot - is mixed in with "cold" code - code that's rarely executed - at an instruction-level; a cache line may contain 2 or 3 hot instructions and a lot of cold instructions.

This means that application processors are prefetching more useless instructions than ever before, clogging up their i$ and causing $ misses. The authors present a tool / database examining these patters (which they used to figure out the above information) and a few mitigating techniques (better code layout that's sensitive to the i$ eviction patterns that they learned about with their database, and new instruction prefetch hints that were chosen using what they learned about from their database).

One big takeaway of knowledge that I can transfer: profiling of applications running in the wild can give you insight into what u-architecutral extensions might address failure modes; in this case, the authors profiled code to figure out what sort of i$ prefetch hints would help them the most.

Hot takes:
personal interest: 5/10 (from transfer knowledge potential)
paper quality / novelty: 7.5/10 (surprised that this is novel. Good idea, but can't believe it hasn't been done to death already)

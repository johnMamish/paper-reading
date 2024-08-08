## A VLIW Architecture for a Trace Scheduling Compiler
#### Colwell, Nix, et. al, 1988
#### Summary
(At the time of writing), taking advantge of instruction-level parallelism (ILP) had the opportunity to speed up computation by 100s of %. Contemporary works, however, fell into 2 categories: (1) claims that the ability to perform ILP was too severely restricted by branching, and (2) systems that used complicated and expensive hardware to achieve modest speedups.

The authors introduce a new architecture and compiler which uses a "Very Long Instruction Word" (VLIW) approach. This approach allows for the scheduling of overlapping instructions at runtime instead of compile time. Previously, taking advantage of compile-time ILP had proven to be intractable due to program branching, but the authors introduce middle-end code transformations in their compiler which make compile-time ILP possible. They perform statistical analysis on branches and merge basic blocks together. Code detects compile-time branch mispredictions and "compensation code" (which I take to mean code that undoes the mispredicted operation) is inserted to handle mispredictions. Furthermore, they also use an "interleaved memory system" instead of a cache, this means that memory reads aren't cached, but instead are performed in an efficient order, determined at compile time.

The authors successfully compiled and ran UNIX for their VLIW processor using the compiler they developed. Disappointingly, I couldn't find any concrete benchmarks for program throughput.

This is a very old paper - it seems like history has decided that VLIW Is not the way to go. I'm sure there's lots of interesting research I can read in the interceding years about attempts to make VLIW work.

Interesting thought - VLIW for power saving? hmmmmmm

#### Strengths
  - Massive and impressive engineering undertaking
	  - Built a CPU back in the days when they had to spread it across multiple PCBs
	  - Built a compiler that used some strange transformations ("compensation code")
	  - Successfully ran UNIX on their CPU
  - Excellent and super-in-depth system overview. Paper is a delight for systems nerds.

#### Weaknesses
  - Severe lack of experiments.
	  - Would love to see more about their profiling compiler (was it good at profiling?) 
	  - ACTUAL system performance (what was typical VLIW throughput? what was speedup compared to more conventional architectures?)

#### Additional comments
This paper is of massive historical interest. Some of the people who worked at the company that published this work went on to work on Intel's doomed flagship VLIW processor (Itanium). This paper is understandable as the intellectual parent of Itanium.

History has shown that the VLIW experiment miserably failed - at least in Intel's hands. Instead run-time parallelism has become the norm instead of compile-time parallelism. 

#### What potential directions of future work remain (if any)?
This is an ancient paper and VLIW has been firmly ground into the dust as a concept.

HOWEVER. I wonder if a restricted subset of VLIW could be an interesting direction for low-power computation. Perhaps Brandon Lucia's MANIC work is VLIW In all but name....

#### Citations
Cites the Tomasulo paper, which is pretty fun.

Keywords: [[architecture]], [[compilers]]
Tags: [[influential]]
Read date: [[july]]
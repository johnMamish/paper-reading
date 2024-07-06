## Quantifying the Cost and Benefit of Latency Insensitive Communication on FPGAs
#### Kevin E. Murray, et. al, 2014
#### Summary
Interconnect delays between large design blocks in FPGAs is growing, even as feature sizes shrink. This means that, late in the place-and-route cycle, we may find that we need extra pipelining registers in the interconnect between two functional blocks. Latency Insensitive Design (LID) is an idea formalized in 2001 where communication between large design blocks can take a variable number of clock cycles. This gives the synthesis engine flexibility about placing delays in communication paths; the needed delay may not be known until late in the synthesis flow, but that's ok because a design adhering to latency insensitive principles can handle extra delay.
LID has been pretty well characterized in ASICs, but not in FPGAs. This paper discusses alternative techniques to LID, shows some typical LID schemes for making a design latency-insensitive, proposes some optimizations to the discussed LID schemes, and then characterizes the resource overhead of LID implementation on their FPGA family. They add both LID and non-LID pipelining to a simple FIR filter design and compare the results. The resource overhead due to LID is modest, ~10% (table 2), but LID actually *lowers* Fmax for the design. Although it doesn't do well on this specific design, this doesn't invalidate LID as a technique; it's possible that LID will show improvements on larger FPGAs, that different designs will reap more benefit from LID, or that the tooling they used can't handle LID properly.
It's hard to make conclusions about the promise of this technique without further experimentation, but this paper provides a good reference for LID in FPGAs.

#### Strengths
  - Good reference / overview of LID techniques
  - Offers a design improvement on a classical LID technique that improves LID Fmax without significant area overhead
  - Extremely apples-to-apples comparison between LID design and non-LID pipelining

#### Weaknesses
  - Experimental scope is limited.
	  - Should have more example applications than FIR filter or better discussion of whether other applications would "play" better or worse with LID than example FIR filter
	  - Should have tried other FPGA families
  - Experimental discussion should have covered toolchains. How aware of LID was the toolchain? Were there experimental toolchains that could have "played" better with LID?

#### Additional comments
Interesting work with valuable overall discussion of LID techniques, but experimental scope was extremely limited. Broader experimental scope could have turned a good but limited paper into a GREAT paper.

#### What potential directions of future work remain (if any)?
 * Would like to see further work about LID awareness in toolchains for FPGAs specifically.
 * Extend experimental scope by using other FPGA families and other applications than FIR filter

#### Citations
Some comments about the citations
 - Theory of Latency-Insensitive Design
   This paper is highly theoretical, but lays the groundwork for LID
 - 

Keywords: [[keywords/FPGA]], [[keywords/architecture]], [[cad]]
Tags: 
Read date: [[read date/2024/june]]

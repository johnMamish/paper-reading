## A Resource-Efficient Pipelined Architecture for Real-Time Semi-Global Stereo Matching
#### Zhimin Lu, Jue Wang, Zhiwei Li, Song Chen, and Feng Wu, 2022
#### Summary
It'd be nice if we had depth cameras that can operate in real-time and on the edge; one promising technique that can get depth images from conventional images is stereo imaging. In spite of the huge amount of work that's been done on stereo imaging, systems to perform stereo depth imaging in real-time on the edge on a low-power system have been limited. In this work, the authors design and test an FPGA based system that's capable of generating stereo matches from 1280x768 images in real-time.

The authors build on prior work which shows that a **consensus transform** is a viable way to perform stereo matching. The authors architecture is pipelined and consists of 3 main modules: a **consensus vector computing unit**, which takes in image streams from each separate camera and performs a streaming consensus transform on them; a  **cost aggregator**, which merges results from between the 2 images; and some **filtering** that post-processes the results.

The authors characterize their work by running a simulation of their architecture on several benchmarks. They also synthesize their hardware for 2 (pretty large) Xilinx FPGAs and show resource consumption. My intuition tells me that their work would fit into a ~1Watt system. This work appears very solid in terms of engineering effort. 
#### Strengths
  - Very impressive engineering effort.
#### Weaknesses
  - The FPGAs that they're using are pretty huge
  - No discussion of power consumption
  - Writing-wise, a ton of time is spent in poorly written explanations that get way too deep into the hardware architecture.
#### Additional comments
I wonder what the background work in this lab was like when making this system... Did they have most of the FPGA dev work already done? what was their foundation like? Or was all of this a massive amount of elbow grease from the ground up?
#### What potential directions of future work remain (if any)?
I'd be interested in seeing this work actually operate in real-time on real hardware.
#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[keywords/3d-imaging]], [[FPGA]]
Tags: 
Read date: [[read date/2024/november]]
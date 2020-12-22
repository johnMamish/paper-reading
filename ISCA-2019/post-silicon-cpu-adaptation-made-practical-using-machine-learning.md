Hot takes:
personal interest: 6/10
paper quality/novelty: 6/10 (playing ML mad-libs with a well-researched problem. but... it does work nice.)

Some workloads are better suited to multi-issue, out-of-order pipelines than others. Whereas workload A might achieve much better IPC on an 8-way superscalar OoO processor than on a 4-way superscalar OoO processor, workload B might not do any better on the 8-wide processor, and the extra 4 execution pipelines will just burn power.

This work improves performance per watt (PPW) while not letting IPC suffer too much (determined by an "SLA") by dynamically turning on and off 4 lines of an 8-wide superscalar OoO processor. They do this predictively by using an ML model running on a management co-processor. For each block of 10k - 100k instructions, BEFORE they execute, the ML coprocessor tries to determine whether the processor should be 8-wide or 4-wide.

They evaluate their design using a cycle accurate Intel skylake simulator that they developed in-house along with a power model by Haj-Yihia et. al (see secontion 3).

Because their ML predictor is running on the firmware of a much lighter-weight co-processor, post-silicon improvement are possible.
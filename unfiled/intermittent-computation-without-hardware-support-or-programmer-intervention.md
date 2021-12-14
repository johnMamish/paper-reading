As batteryless devices become commonplace, methods to more easily make code run on intermittent systems will become important. The authors introduce Ratchet, an LLVM compiler pass that breaks code into "idempotent" blocks by detecting Write-After-Read (WAR) data dependences and inserting lightweight checkpoints before them. If any idempotent block of code is interrupted by a power outage, execution can safely be re-started from the beginning of the block. The authors protect against power outages DURING checkpointing by using a checkpoint double-buffering scheme.

As far as I can tell, this method only works on microcontrollers that have FRAM main memory; Ratchet's main function is backing up volatile CPU registers, which it does by using nonvolatile FRAM. The authors run Ratchet in simulation, showing that Ratchet allows execution of programs that would have otherwise failed, but with a reasonable amount of overhead (Figure 6).

Hot takes:
personal interest: 9/10

paper quality / novelty: 9/10
## Exploring the Design of Energy Efficient Intermittently Powered Systems using Reconfigurable Ferroelectric Transistors (R-FEFETs)
## Sandeep Thirumala, Arnab Raha, Sumeet Gupta, Vijay Raghunathan, 2021

#### Summary
Intermittently Powered Systems (IPSes) typically need to checkpoint their data in non-volatile memory so that forward progress can be continued if power is lost unexpectedly. Unfortunately, checkpointing takes a lot of time and power; a lot of recent work in IPSes has been aimed at figuring out the best time to make a checkpoint. Some researchers have also looked at just replacing all of the memory in a microcontroller with nonvolatile memory, which would remove the need for checkpointing. There are many different types of nonvolatile memory technology to choose from, but they suffer from different issues (Section I, paragraph 3).

The authors identify Ferroelectric FETs (FEFETs) as a potential NVM technology for this application. Current FEFETs suffer from a lot of issues, but in a previous paper, the authors have introduced a new type of FEFET - the Reconfigurable-FEFET - which they contend addresses many of these problems (Section I, paragraphs [4, 5]). By adding a metal layer beneath the FEFET's ferroelectric layer and another stack of ferroelectric material connected to a "control" gate, the authors make a 4-terminal "R-FEFET". The R-FEFET can be switched between a "volatile" and "nonvolatile" state using its control gate; moreover, the R-FEFET is much more energy efficient than other FEFETs (Section III). The authors also introduce 3 circuits - 2 Flip-flops and 1 3-T memory cell - which use the R-FEFET as a non-volatile storage element while still having a sufficiently simple operating sequence that they can operate directly inside of widely-used FF and RAM circuits.

In simulation, the authors validate the read and write performance of their R-FEFET-based FFs and RAM cells. Their cells consume less energy than similar FEFET based cells (Figure 10). The authors also make a microcontroller which uses their R-FEFET-based FFs and SRAM cells instead of corresponding volatile cells. They run several benchmarks to show that the use of their cells reduces power consumption. They also find that the power savings are much more significant when main memory is replaced with R-FEFET based cells than when FFs are replaced.


#### Strengths
  * Great systems application of a novel beyond-CMOS device
  * Very strong design work; they show 3 new circuits and validate them individually and as part of a system in sim.
  * Simulated experiments are carried out on isolated devices and on the whole system.

#### Weaknesses
  * Incomplete but still overly-technical explanation of R-FEFET operation. If someone wants to know the gory details, they can read [19, 20]. IMO this paper should present it in an easier-to-understand way.
  * Difference between what they mean by "volatile" and "non-volatile" mode not super clearly explained.
  * The writing poses R-FEFET as if its main advantage is the addition of the 'C' gate, but it seems like it is just a better FEFET overall.
  * Zero discussion of fabrication of real devices.
  * Not sure if energy improvement due to addition of R-FEFET FFs is really apples to apples, maybe selling R-FEFET FF energy savings short. If they used R-FEFET FFs in a system with a different NVM checkpointing technology than 3T R-FEFET, the use of R-FEFET FFs would probably be higher impact.

#### Additional comments
I would like to see a clearer explanation of the "non-volatile" vs "volatile" mode. I think these "modes" may be inappropriately named. A scattered and opaque technical description is given, but considering the naming of these operating modes, I would think that there is a more intuitive explanation.

#### What potential directions of future work remain (if any)?
Important for this to be validated in a real system. Neither of their previous works on R-FEFET [19], [20] fabricated real devices.

Would like to see these potentially used in NV-FPGAs and compute-in-memory circuits.

#### Hot takes:
personal interest: 9/10\
paper quality / novelty: 7.5/10\
For all of the gripes I have, this is a great paper incorporating solid, significant design work, based off of a really novel idea.

## ELI: Bare-Metal Performance for I/O Virtualization
#### Abel Gordon, Nadav Amit, Alex Landau, et al, 2012
#### Summary
(At the time of writing), Virtual machines are extremely promising for many applications, however, I/O performance when running a VM is limited, especially when interrupts are required for processing I/O. The reason being is that - in typical VM enviornments - each interrupt requires 2 time-consuming context switches to the hypervisor: one when the interrupt starts and another when it stops. For I/O intense workloads (~100k of interrupts per second), this can limit VM performance to ~50% of bare-metal performance, whereas with little I/O, VM performance approaches 100% of bare-metal performance.

To address this issue, the authors introduce Eli, an interrupt virtualization strategy that avoids switching out to the hypervisor. They do this by constructing what they call a "shadow interrupt table". Interrupts that are handled entirely by the guest have their shadow entries pointing directly to the guest's interrupt routine, but interrupts that need host intervention go out to the host; implementation details are described in chapter 4. Because interrupts are now delivered directly to the guest, the guest can enable or disable interrupts, meaning that it could "starve out" the host CPU. To address this issue, ELI utilizes the x86's preemption timer, which unconditionally returns to the host after a certain amount of time. This and other security concerns are addressed in chapter 6.

They evalute their method by running 3 common VM workloads with a baseline VM environment where all interrupts are handled by the host before guest processing and 2 variations of ELI, one where interrupt entry bypasses the host and one where entry and exit both are handled by ELI. Full ELI reaches nearly 100% of baremetal performance for the workloads. They also look at interrupt rate vs speedup and find that ELI speeds systems up the most when there are many interrupts.

This interesting work is directly applicable to datacenters. I remain a little unconvinced of ELI's security, but these concerns could easily be assagued with some arch extensions.

#### Strengths
  - Massive improvement on I/O workloads
  - Applicable with no hardware modification
  - Good experiments that provide explainability of technique

#### Weaknesses
  - Security feels a little questionable. Would have liked a further treatment of that - I imagine that real damage could be caused even with the preemption timer limiting things
  - limited to x86 (but this isn't really the authors fault)

#### Additional comments


#### What potential directions of future work remain (if any)?

#### Citations

Keywords: [[keywords/operating-systems]]
Tags: [[tags/influential]]
Read date: [[july]]
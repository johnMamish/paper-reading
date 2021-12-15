#### Summary
Traditionally, FPGAs are hierarchically broken into tightly-connected "local clusters" of LUTs with local interconnects, which are more loosely connected by global interconnects. In larger process nodes (16nm and up), the thin but short wires that make up local interconnects have less delay than the long but thick wires that make up global interconnects. However, as process nodes continue to shrink, growing wire resistance threatens to flip this paradigm on its head, making local connections slower than global connections. The authors extrapolate from literature and open-source tools to estimate device parameters like metal layer stackup, wire thickness, and tile layout. They validate their estimates by comparing with measurements from actual FPGAs (I think??). They use their estimates to model the effect of changing "local cluster" size on total FPGA propagation delay.

AFAICT, the major findings are summed up in Figure 13; as technology nodes shrink, cluster sizes of 2, 4, and 8 remain acceptable and a cluster size of 16 (which is fine at a 16nm node) gets worse and worse. Even then, some future technology nodes might result in higher propagation delay. The takeaway is that FPGA architecture might need to change to accomodate shrinking node sizes.

#### Hot takes:
##### Personal interest: 6 / 10
I like the FPGA angle, but the concerns are related to super-high performance at state-of-the-art process nodes, which doesn't describe the type of system I am currently doing research with. UNLESS.... this spirit of work could be abstracted to a low-power angle instead of a high performance angle.

##### Paper quality / novelty: 7 / 10
The paper tackles a large-scale upcoming issue in a big domain. I would have liked to see more info about how they simulated and came to their modelling conclusions, but maybe it's assumed that people working in this area will already know all about that stuff.

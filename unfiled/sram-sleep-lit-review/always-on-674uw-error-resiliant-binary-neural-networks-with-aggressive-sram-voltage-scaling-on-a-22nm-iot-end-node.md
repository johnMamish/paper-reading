Working off of the observations that
  * binary neural networks (BNNs) are especially resiliant to bit-errors when compared to traditional DNNs because all bits have the same computational importance (whereas in a DNN the MSBs are more important) and
  * SRAM retention degrades slowly as vsupply drops
The authors design an SoC for evaluating BNNs which has significant power savings due to seperate SRAM power domains. There is a system power domain for the core of the SoC and the SoC's core program memory, and then there is a seperate, undervolted power domain which contains the BNN's SRAM for inference. This undervolted SRAM consumes much less power than the properly volted SRAM in the SoC's core, at the cost of a bit-error rate of ~0.1%. I think that figure 13 is supposed to illustrate this, but it's not clear to me.... why does the green bar increase as the SRAM's Vdd goes up??

Hot takes:
personal interest: 7/10
paper quality / novelty: 7/10  (kinda solid paper, but not very novel)
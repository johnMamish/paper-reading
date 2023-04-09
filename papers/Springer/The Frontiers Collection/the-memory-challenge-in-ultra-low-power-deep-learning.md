## The Memory Challenge in Ultra Low-Power Deep Learning
#### Francesco Conti, Manuele Rusci, Luca Benini, 2020
#### Summary
Deep Learning is a widely used computational tool; it holds promise to improve the effectiveness of edge applications, but as networks become more sophisticated, they're only becoming larger. This is at odds with the scaling requirements of edge applications, which can't use on-chip SRAM because its too large and can't use off-chip DRAM because it's too power intenstive. The authors investigate the roots of this issue and describe some potential mitigations.

The authors start with an analysis of the problem. Regardless of how networks are structured, significant bandwidth to off-chip DRAM will be necessary. They find that the DRAM itself does not consume much power, but instead it's the memory transfers (in fact, DRAM retention is extremely cheap per-bit (table 19.3)). They discuss techniques for mitigating this problem; the most prevalent is the removal of cache management circuitry from DL ASICs, instead opting for compile-time determination of optimal memory management techniques. They also discuss PULP, a widely used, open-source framework for highly parallel computation.

The authors conclude by discussing a potential memory hierarchy for ultra low-power deep learning systems which integrates on-chip SRAM, STT-MRAM, and DRAM. By engineering memory accesses to reduce off-chip bandwidth, we can reduce power significantly.

#### Strengths
  - Survey of a problem that doesn't get enough attention

#### Weaknesses
  - Lacks a listing of open problems (that would be nice)
  - May have tunnel vision on a few specific approaches
  - Fumbled some figures (what's going on with 19.11??)
  - Some tables would be much better as graphs

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?

#### Citations
 - [[dory-automatic-end-to-end-deployment-of-real-world-dnns-on-low-cost-iot-mcus]]

Keywords: [[deep-learning]], [[low-power]], [[keywords/architecture]], [[keywords/memory]]
Tags: 
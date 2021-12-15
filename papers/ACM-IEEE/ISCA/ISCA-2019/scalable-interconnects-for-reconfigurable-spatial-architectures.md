Research Opportunity: I've never heard of coarse grained reconfigurable array (CGRA)s before. Like an FPGA but just functional blocks (EBR, DSP, etc) without the fabric. Wonder if/how this could be used in low-power land.

Because their memory access patterns are more deterministic and less bursty than those of CPUs, CGRAs have different requirements for system busses. In this work, the authors characterize the bus needs of CGRAs and introduce a CGRA synthesizer that is network capacity aware. They give special attention to hybrid networks which consist of a higher-bandwidth but less flexible static network AND a NoC. Their synthesizer can put predictible, high-bandwidth, low-latency traffic on the static network and bursty, lower-bandwidth traffic on the NoC (section 3.1.3).

Hot takes:
personal interest: 5/10 (extra points cause I've never heard of CGRAs before)
paper quality: 7/10
~136 citations, 2008

The authors propose a "mixed bag" of 5 orthogonal strategies for decreasing SRAM power consumption. They take strategies from "traditional" low-power digital design (floating bitline), near/sub-threshold computing (by sizing transistors cleverly, having a replica bitline for bitline precharging, and scaling freq down aggressively with voltage (section IV), AFAICT), and dark silicon concepts (shifting both vcc and vss, which is necessary for their near-threshold design (because of margins) and which saves more power (because raised vcc means less leakage) but requires an external supply above vcc).


Hot takes:
personal interest: 5/10 (It's good for me to know about these techniques for context, but I don't think I can add onto them; the paper is 12 years old and outside of my wheelhouse)
paper quality / novelty: 8?/10  (I know it's an old paper, but still)

Research opportunity: This is orthogonal with keeping SRAM in low-power retention states and prefetching.
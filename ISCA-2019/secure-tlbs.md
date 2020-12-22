Using timing side-channels in TLBs is similar to attacks like Spectre and Meltdown. For reasons that aren't clear to me, the authors of this paper appear to claim that proposed defenses against Spectre and Meltdown won't help with TLB-based attacks. They propose a method for enumerating all possible TLB sidechannel attacks (section 3) and 2 example secure TLB designs that were created with information from their sidechannel analysis. The sidechannel analysis seems sound to me, but I don't know how much I like their mitigation methods. Their partitioning method requires victim processes to be specified; their "random fill" method look like it would cause very significant slowdown.


Hot takes:
personal interest: 3/10
paper quality / novelty: 6.5/10  (analysis: good. mitigations: meh.)
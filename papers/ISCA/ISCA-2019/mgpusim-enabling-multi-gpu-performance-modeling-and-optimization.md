Hot takes:
personal interest: 2.5/10
paper quality/novelty: 7?/10

As parallel computing workloads grow, multi-GPU systems are becoming common. (It's beyond the scope of this paper what constitutes a multi-gpu system, and how market forces in the coming 5 years might lead us to one gigantic GPU instead of 8 GPUs on seperate dies with seperate memories and more throttled interconnect, but this research might still be relevant even in a situation like that (right?)).

A lot of potential performance gains are left on the table when programmers try to adapt single GPU code to multiple GPUs, often related to memory bandwidth and access patterns. Tooling doesn't exist to efficiently simulate multi-gpu systems thereby hampering software development for multi-gpu systems.

The authors introduce a new multi-gpu simulator. The design of their system is well-principled and is driven by a few cool but common-sense design rules that they outline in section 2.3. They also introduce 2 new multi-gpu programming techniques that significantly improve multi-gpu performance which they have validated with their new simulator.

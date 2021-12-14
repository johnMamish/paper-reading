Hot takes:
personal interest: 4/10
paper quality/novelty: 7.5/10

Operations on large graphs are a common workload among broadly different fields. Graphs are growing to take up many many terabytes, meaning that large graphs must be stored in SSDs as they're operated upon.
Existing work uses the SSDs "normally": the API to the SSD uses page accesses and writes, which are generic primitives for handling arbitrary block data.

This work proposes a new SSD "interface" which has semantic awareness of graphs built-in. This allows for more efficient storage of graphs, meaning that fewer pages have to be read from the SSD in order to perform common graph operations. Moreover, because the underlying structure that they propose isn't a generic block-based memory for holding generic data but is instead specialized for holding graphs, the number of writes to update a node or subgraph can be drastically reduced; write-amplification can be mitigated.


Research Opportunity: beyond-cmos heterogenous version of this. Are there smaller data structures within the SSD that are updated more often (e.g. count of connectinons coming from a certain node) that can be stored in less-dense, higher-perfomance memory. e.g. you have 64 bits of MRAM for each 4kbit page of flash.
Hot takes:
personal interest: 7/10
paper quality: 7/10

The authors add small amounts of additional "copy-row" ("CROW") control circuitry to DRAM chips which enable some novel operations. Specifically, they designate some rows as "copy rows" and add circuitry that efficiently copies select "normal" DRAM rows to the copy rows. The authors propose that many possible system performance improvements can arise from using this copy-row circuitry with different memory controllers.

They demonstrate 2 potential applications:
  1. caching: Moving a DRAM row to a copy row decreases access time because of read amplifier drive strength. By identifying which rows are accessed most often, read latency can be decreased for those rows.
  2. refresh time lengthening: DRAM refresh rate is determined by the "weakest" cells on a chip - cells which hold charge worse than other cells. By profiling the memory at boot time, the weakest cells can be identified and remapped to copy rows, thereby allowing longer refresh intervals. Longer refresh intervals mean less power consumption and lower likelihood of a refresh operation conflicting with an access.

Research Opportunity: this work makes me aware of the existance of "strong" and "weak" DRAM cells and inspires me to look at ways to have very low-power DRAM by altering DRAM read/write circuitry. To do this, I'd need to profile power consumption of a DRAM chip.
  * How much comes from refresh?
  * How much from communication?
  * How much from read/sense?
  * How much from write?
I'd also want to look into how much chip capacity we'd lose if we didn't use rows containing the weakest cells. I'm sure that this paper has some analysis about that sort of thing.
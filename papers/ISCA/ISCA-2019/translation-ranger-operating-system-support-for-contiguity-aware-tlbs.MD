TLBs take up a lot of space and power in modern processors. Traditionally, TLB page sizes are fixed, which means that more TLB entires are needed as you use more memory, leading to TLB thrashing. Because many applications just need a couple enormous contiguous chunks of memories, TLBs with variable page sizes are emerging, significantly reducing the number of TLB entires needed (figure 2). Unfortunately, operating systems don't have the mechanisms to effectively utilize TLBs that enable enormous pages; as processes run, fragmentation occurs, and you're back to where you started, needing a bunch of TLB entries.

The authors propose an OS service that runs periodically, coalescing fragmented memory regions into large contiguous areas. This takes advange of variable-page-size TLBs whereas previous works couldn't.

It's not clear to me how much architectural support is needed; they probably discuss, but didn't have time to read. Also, I don't know how they get out of unnecessary copying. Seems like copying to coalesce pages would take a shit-ton of time. They probably also discuss this.

Hot takes:
personal interest: 2/10
paper quality / novelty: 7/10
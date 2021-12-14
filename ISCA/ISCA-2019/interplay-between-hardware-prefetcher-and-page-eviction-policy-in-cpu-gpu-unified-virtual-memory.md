Recent memory management improvements - namely unified virtual memory, which supports on-demand paging and automatic page migration for GPUs - have been important in making GPUprogramming tractable for non-specialist GPU programmers. However, contention between the GPU hardware prefetcher, loss of locality due to page migration virtualization schemes, and eviction strategies can end up being very very counterproductive for performance. The authors address this issue by some "pre-eviction policy" stuff I don't really understand, but it does make performance way better.

This paper is a good example of how 2 techniques that individually improve performance can destructively interfere to make things much worse, and is a good case study for mitigating this issue.

Hot takes:
personal interest: 3/10
paper quality: 7?/10

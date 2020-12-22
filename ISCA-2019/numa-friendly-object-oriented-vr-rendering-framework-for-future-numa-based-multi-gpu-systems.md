Hot takes:
personal interest: 2/10
paper quality/novelty: 7?/10

The authors observe that - because of resolution and latency requirements - VR requires drastically ( > 1 order-of-magnitude) more GPU computation than other graphics workloads. In scaling up GPU performance for VR, Non-Uniform Memory Architectures (NUMAs) are an important technique for "sewing together" multiple GPUs. Because of the overlap between field-of-view for VR goggles, there are many objects which will have to be shared between the 2 frames, providing opportunites to inform the system about which objects to be rendered should be placed where in memory.

Figure 17 is pretty cool: it shows that their technique is basically the same as getting a bunch of free GPU bandwidth.

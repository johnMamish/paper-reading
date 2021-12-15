GPUs have much higher memory bandwidth requirements and less space to turn into caches than CPUs do, leading to really bad cache thrashing. A method called warp throttling has been proposed where ?some warps in the GPU are turned off so that their cache space can be used?, but the register files in these idle warps sit unused; because of GPU microarchitecture, register files in warps constitute quite a bit of space, comparable to an L1 cache. The authors propose Linebacker (great name!) as an alternative(??) to warp throttling where warps that are unused back up their register files to DRAM during the period of their disuse and then allow their register files to be used as L1 cache space for active warps.

It seems like warp throttling and Linebacker are almost entirely orthogonal, but the authors imply that they aren't orthogonal without really explaining why.

Hot takes:
personal interest: 4/10
paper quality: 5/10 (seems like a good idea, but it's pretty badly explained and there appears to be some significant orthogonality that's either not explored at all because the authors don't understand it or (more likely) they totally fail to explain the lack of orthogonality clearly).

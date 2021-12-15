The quality and latency of a DNN result can be determined by energy budget. If a system has more energy available, it can use a more sophisticated model evaluated more quickly to give better results; if a system has less energy available, nominally correct results will still be available, they will just be degraded.

The authors leverage this observation to opportunistically speed up DNN computation with harvested energy. They introduce a system with 2 seperate power domains, one of which is battery powered and the other of which is powered by harvested energy. When harvested energy is available, an accelerator in the harvested energy domain performs extra computation to improve the DNN results.

The authors also present a nonstandard type of floating point (??) which they claim improves DNN accuracy over both fixed and floating point while having similar power consumption to fixed point. If their claims are right, it would be a very cool result.

I'm bothered by how the authors present this paper; I find it somewhat misleading and also restricting. I think that they would be better served by going a "Tragedy of the Coulombs" approach.

Hot takes:
personal interest: 6/10
paper quality / novelty: 6/10
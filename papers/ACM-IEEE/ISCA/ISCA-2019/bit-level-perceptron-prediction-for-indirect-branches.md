Hot takes:
personal interest: 5/10
paper quality/novelty: 6/10

random thought: potential beyond CMOS app: CAMs like Branch Target Buffers

In modern programming workflows with standard computer architectures, indirect branches are a fact of life. They aren't very fun because - unlike conditional branches with a fixed target where the branch predictor has to guess a 2-answer multiple-choice question right - the branch predictor has to guess a many-answer multiple choice question right to avoid misprediction penalties.

This is a well-researched problem. People have tried to do this at software compile time, but it requires solving an NP-hard "static type inference" problem or doing extensive profiling. runtime, microarch techniques have proven much more promising. Typically this is solved with a Branch Target Buffer, but these are power hungry and big.

Other people have tried to solve this problem with neural nets, where one net picks a single branch target from many, but the authors have a new approach where there are many networks in parallel, and each one predicts a single bit of the target address (section 3.2).

Crossbars consisting of resistive memory devices have potential to perform processing in-memory operations which are especially conducive to accelerating machine learning. Unfortunately, these systems suffer from a few drawbacks: manfacturing difficulty, inaccuracy due to process variation & ADC/DACs, and the size & energy consumption of ADCs/DACs all hamper adoption of analog PIM for neural network acceleration.

The authors present FloatPIM, a controller for memristor memory crossbars which stores floating point numbers in ieee format in the memory array and performs floating point addition and subtraction directly in memory using the resistance of the memory elements. This move from analog to digital gives us the long-known benefits of totally eliminating noise, and it makes this sort of PIM system much more feasible for manufacture.

Hot takes:
personal interest: 6/10
paper quality / novelty: 8.5/10 (would score higher if eval was in real hardware not sim.)
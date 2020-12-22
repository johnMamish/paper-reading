Watering lawns consumes far more water than is required to maintain them, which is a major environmental problem. Past work has tried to design sprinkler systems which optimize moisture delivery to lawns by relying on a centralized node, but these systems suffer from a single point of failure and require battery replacement. The authors present a distributed batteryless system which consists of "smart sprinklers" outfitted with moisture sensors, compute units, and radios. They harvest energy from water pressure and only require communication with nearby sprinkler units. Over time, they learn a model to predict moisture by communicating with nearby nodes. Learning and evaluating the model takes more computational power than the microcontroller that they use for system control has, so they also include a power-gated raspberry-pi zero. Their system maintains similar moisture levels as previous work (Figure 5,6) while taking much less water (Figure 7,8).

Hot takes:
personal interest: 6/10
Environmental impact; classic "power-gate the big compute" strategy.

paper quality / novelty: 7/10
Pretty good concept that's slapped together with hobbyist-level hardware.
I almost had an aneurysm with the sentence "we design our own system management chip to meet the requirements of our application" (Section 4.3, paragraph 2), but whatever.
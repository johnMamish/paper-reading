The authors present a method by which the phase and RSSI change over several frequency bands of commodity RFID transmission can be use to differentiate between materials. Several challenges that need to be addressed for this sort of material sensing to work: phase dependance on distance, random rotation of RFID tag located on target material, RF reflectivity of some materials, and multipath effects. They test a few methods for solving these issues, respectively: taking readings at several arbitrary distances, looking at the shape of phase change over freq instead of absolute phase value, (idk how they handle rf reflectivity of some materials (see Section 4.5), and using a directional antenna + finding frequencies with less multipath. They use a "dynamic time warping" algorithm to classify materials.

Hot takes:
personal interest: 4/10
Cool RF stuff. Not that relevant to me.

paper quality / novelty: 7/10
Good treatment of the topic, but I suspect that this work has been done a lot before. I disagree with their argument in section 1 that using RFID tags instead of a fixed RX/TX is really all that useful, but maybe their work will let people use cheaper / more flexible commodity RX/TX units for this sort of materials analysis.

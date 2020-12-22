Taking advantage of weight-level sparsity in neural networks is a pretty hot topic (and for good reason), but no one is talking about bit-level sparsity! The authors claim that over 90% of the bits in 16b fixed-point image classification models are 0 (Section 1, "Contribution #1"). Laconic avoids unnecessary bit-operations by introducing an entirely new type of MAC unit which operates on a new format of number (section 3.2). There is some interesting reading and digesting to do in section 3 if I want, but it would take a bit of thinking to figure it out.

Speedup / power savings appear good and I THINK that they should be very good, but for some reason I found their results section to be pretty uncompelling. Could just be that I gave this a 10-minute one-pass read.

Hot takes:
personal interest: 7/10
paper quality / novelty: 7/10 (would have scored this higher if not for what I consider to be a shaky results section).
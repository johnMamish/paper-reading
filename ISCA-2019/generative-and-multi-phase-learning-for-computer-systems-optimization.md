Hot takes:
personal interest: 7/10
paper quality/novelty: 8.5/10

Computer systems are exposing more and more points of their architecture for management, e.g. clock speed, system voltage, number of cores, etc. Improved system performance and power consumption can be achieved by allocating these resources optimally for each problem, but as the number of points has gone up, the state space as exploded and the only way to manage all of these options is with ML/AI.

The authors claim that a lot of research in this area tries to improve resource allocation and therefore system performance by using the latest ML research. However, they claim that we have reached a point of severely diminishing returns, that improvements in predictor accuracy won't help much when it comes to overall system performance metrics. The best thing to do is to instead focus on selecting from between a few optimal points.

They propose 2 methods for doing this
  * generating more datapoints for training models (not clear to me how this relates to their thesis)
  * selecting a few optimal performance points for the system and then having the management systems just choose between those points instead of letting them wander throughout the whole state space, which includes a lot of shitty states and is difficult to train over.

This paper has some surprising and "against the grain" conclusions that I really like, but I didn't give it a close enough reading to fully understand what they were saying beyond their thesis statement.
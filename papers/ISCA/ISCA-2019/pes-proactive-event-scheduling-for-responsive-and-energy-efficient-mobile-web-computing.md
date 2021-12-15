Hot takes:
personal interest: 2/10
paper quality/novelty: 7?/10

This paper basically introduces speculative execution for web browsers.

The state of the art solution is to wait for a user to interact with a webpage and then compute the result of the interaction, but this often results in webpages that appear sluggish or unresponsive.

The authors propose the use of a learner to determine which user actions are most likely, and then speculatively evaluate those actions that are deemed most likely. This provides benefits on TWO fronts: it makes pages more responsive, AND, because CPUs can be clocked less aggressively because speculation gives the system more room to satisfy QoS / latency requirements, it saves power.
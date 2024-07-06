#### Chun Wei, Zhe Zhang, Wei Qiao, Liyan Qu, 2015
#### Summary
In order to harvest the maximum amount of power from a wind turbine, there's an ideal rotor speed for each wind speed; too slowly and the rotor is underloaded, too quickly and it's overloaded. Tracking this ideal speed requires calibration data to be collected for the rotor and installation of an anemometer, which the authors contend is prohibitive.

The authors apply a classic table-based Q learning approach, using an RL agent to select target rotor speeds. The state that the agent observes (equation (5)) is rotor speed & power, and the action thath the agent takes (equation (6)) is an adjustment in target rotor speed.

The authors evaluate their methods with a simulated 1.5MW harvester in both constant and dynamic wind speeds, finding that in each case, the optimal power coefficient is tracked. They also evaluated their method with a direct drive system where a DC motor is mechanically coupled to a PSMG (Permanent Magnet Synchronous Generator), turning it with a computer-controlled torque to simulate wind.

Motivation / Problem: The one sentence summary of the problem this is tackling and why it is important.
Method: How they solve the problem (build a system? algorithm? study?)
Results: Whats the speedup, the outcome, the takeaway.
Future: This is for you to thoughtfully extend or engage the work and what it means.

#### Strengths
  - It works
  - I mean, it sounds like I'm talking it down, but this is a useful method; seeing it in action is important.

#### Weaknesses
  - Justification in the intro seems flimsy
  - Couldn't find details on how they controlled rotor speed?
  - Found graphs with C_p difficult to read / interpret
  - Wish there was a discussion of the computational load for training the Q learner.

#### Additional comments
The premise seems flimsy: that "\[anemometer use\] increases the capital, installation, and operational costs" by an inconvenient amount. Are you trying to tell me that it's fine to dump $5 mil on a 2MW turbine, but collecting some calibration data from it and sticking an anemometer on top is a step too far?
Still, the work itself is very useful, even if it lacks good justification. It can prove useful in smaller, lower-power installations.

Note that in Table A.1, "pu" stands for "per unit", a common convention in motor ratings.

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[keywords/reinforcement-learning]], [[keywords/voltage-regulators]], [[energy-harvesting]]
Tags: [[switching-energy-harvesters]]
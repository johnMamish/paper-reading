NoCs are becoming very large and very complicated, and are beginning to become a nontrivial part of the power budget. Moreover, to address intermittent and permanent faults that are becoming common as scaling to the 10nm tech node pushes forward, error correction and routing schemes are being added which complicate NoC control.

The authors introduce a NoC which has a new (?) combination of router bypass, fault-tolerance, and buffering hardware (section 3). The new hardware that they introduce to mitigate the above challenges comes with control challenges which they solve using a reinforcement-learning agent (section 5). The RL agent's "action space" consists of 5 actions: it can set the NoC mode to any of the 5 operating modes described in section 4.

Hot takes:
personal interest: 4/10
paper quality / novelty: 7.5/10  (as "let's plug in machine learning" papers go, I thought this one was pretty good).
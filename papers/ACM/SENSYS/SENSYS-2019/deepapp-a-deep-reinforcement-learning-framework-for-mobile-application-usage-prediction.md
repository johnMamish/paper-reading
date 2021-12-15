A user complaint in commodity smartphones is the amount of time it takes to open apps. This latency can be slowed significantly by initializing the app before the user clicks on it, but this consumes resources; if the phone is going to speculatively initialize apps, it has to be correct a pretty good percent of the time, otherwise overall system performance will degrade significantly. Predicting which apps will be opened is difficult; it varies both inter- and intra- user; even worse, users may install new apps on their phone on the fly.

The authors propose a reinforcement learning agent to predict which apps a user will open in the next few minutes. The RL agent knows the time of day and a "context feature" (section 3.2) constructed by nearby "points of interest" (section 3.2) that are gleaned from GPS data and presumably local maps. Because there's an action-space explosion for any reasonable number of apps on a user's phone (section 3.3), the authors use a method called "actor-critic agent" to make the Q agent tractable. AFAICT, this involves another network which learns a mapping between a continuous version of the action space and a discritized version. The Q agent outputs actions in the continuous action space (which doesn't suffer from explosion).

One thing I loved about this paper is figure 16. I was thinking that the authors might be gunshy about showing their method with a toooon of apps, but they go for it and test it with a downright silly number of apps (200).

Aside from that.... I really don't think this sort of work is how we should be spending our time. Cool idea, very low-impact end application.

Hot takes:
personal interest: 4/10
example usage of "actor-critic agent" could be useful to me

paper quality / novelty: 6/10
Cool paper, dumb application.
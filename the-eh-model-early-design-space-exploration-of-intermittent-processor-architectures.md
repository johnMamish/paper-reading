Intermittent computing shows promise as a next-generation computing paradigm. The salient trait of intermittent computing systems is their regular loss of power and resultant need for regular backups. This leads to new architectural tradeoffs for architects, compiler writers, and programmers. The authors present "EH", the first model for comparing microarchitectural tradeoffs in intermittent systems.

the authors (quite fairly) state that the primary metric for charactarizing the performance of an intermittent computing system is the proportion of harvested energy that goes towards useful computation. This gets right to the heart of intermittent computing: if no backups are made, all useful computation is lost; if too many backups are made, all power is spent on backing up and no useful computation is done. Many microarchitectural and operatings systems approaches have been proposed to maximize the useful energy done per unit of harvested energy. However there is no one-size-fits-all approach. Depending on the energy cost of different fundamental operations, different systems will favor different approaches.

"EH" exposes several knobs that can be appropriately chosen to model a given system (Section III, table 1). Their model predicts the percentage of power that a system will spend on forward progress given the parameters that characterize the system. Different systems approaches will find different areas in this design space and yield different levels of progress per energy.

I think that the authors could improve their model significantly by considering stochastic effects

Hot takes:
personal interest: 7/10
paper quality / novelty: 7/10
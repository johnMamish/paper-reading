To make batteryless systems feasible, some new programming paradigms have been developed. There's a huge corpus of existing firmware that's not readily compatible with these new programming paradigms; rewriting them to fit the paradigms might be impossible, and rewriting them entirely takes too much engineering effort and is error prone.

The authors identify 3 primary programming utilities / assumptions that existing firmware makes which makes it difficult to port to existing batteryless programming models: assumptions surrounding the "staleness" of data over time, the use pointers, and the use of recursion. Discarding stale data is difficult because of how legacy code handles the passage of time; the authors introduce some new language primitives to handle unexpected delays (section 3.2). To deal with pointers, the authors introduce a new method for tracking memory changes (top of Section 3). To deal with the large stack growth incurred by recursion, the authors introduce a stack segmentation method (top of Section 3). Taken together, these techniques make it much easier to port legacy code to batteryless systems.

The authors demonstrate that TICS (the name of their system) doesn't introduce too much overhead (5.3) and that it's reasonably easy to use (5.4) from an online user study of ~100 people.

Hot takes:
personal interest: 8/10

paper quality / novelty: 8/10
The figures and writing in the paper are extremely good and communicate the problem and solutions very effectively. I'm not fully convinced that these few clever techniques were / are the only thing standing in the way of porting legacy code to batteryless systems with low-effort, but maybe I just didn't read closely enough.
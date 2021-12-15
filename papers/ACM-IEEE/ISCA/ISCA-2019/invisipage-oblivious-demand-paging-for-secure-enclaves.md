To mitigate against an attacker with control of an OS being able to access secure information using paging as a side-channel (as demonstrated in famous paper "Controlled-Channel Attacks: Deterministic Side Channels for Untrusted Operating Systems"), the authors present software and hardware methods for hiding page access info from an operating system, even though the OS is still able to help manage the memory for the victim application. They do this by "[distributing memory management duties between the OS and the victim appliction]" (conclusion). I don't fully understand the method. The authors describe it as being an adaption of "Oblivious RAM" (where RAM accesses are randomized so an OS can't track patterns) to paging.

Hot takes:
personal interest: 3/10
paper quality / novelty: 7/10
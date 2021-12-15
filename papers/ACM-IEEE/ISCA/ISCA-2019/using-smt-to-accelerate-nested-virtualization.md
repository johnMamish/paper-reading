In datacenters that provide things "as-a-service", nested virtualized machines are becoming common. The service provider runs a VM on the hardware, and the user runs a VM inside that VM. Unfortunately, this results in "amplication" of VM traps when the topmost VM tries to trap to the provider's VM (figure 1).

The authors propose a system that can be software-only where the "middle" VM continuously stays running on a seperate SMT thread, asleep for most of the time but ready to start with no latency when it's trapped to. When first reading this paper, one of my major concerns was that this makes the extra SMTcore useless, but the authors claim that in datacenters most SMT cores are disabled for security and performance reasons (side-channel attacks and thrashing). Basically, they're saying "there's an entire unused multithreaded core just sitting here.... what can we use it for?".

In their scheme, they're using 100% unuilized hardware in a way that lowers latency, but only utilizes it to a couple % AFAICT. I think that a follow-up work could provide a more compact microarchitectural mechanism for achieving the same thing in datacenters.

Hot takes:
personal interest: 1/10
paper quality / novelty: 6/10  (cool that they're using typically unused hardware).
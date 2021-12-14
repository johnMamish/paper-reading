Hot takes:
personal interest: 7/10
paper quality/novelty: 7/10

Janus: Optimizing Memory and Storage Support for Non-Volatile Memory Systems

Improving nonvolatile memory technology holds the promise of using NVM for main system storage, which could reduce system cost, power consumption, and improve UX. If nonvolatile memory replaces volatile memory, requirements to read from and write to memory will change. Whereas volatile memory might require ECCs or fast encryption, nonvolatile memory will require stronger encryption and consistency checks so that consistency is maintained even between crashes. These operations incur a lot of computational overhead, which results in bigger latency for basic read and write instructions.

By breaking them down into simpler operations, Janus allows steps required to store data to be executed speculatively, parallel-ly, or out-of-order. This results in significant system speedup for systems where volatile system memory has been replaed by nonvolatile memory and the issues assocated with NVM are now responsibilities of the system.

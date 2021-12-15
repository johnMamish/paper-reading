Memory access patterns are often very regular for a lot of workloads. Traditional prefetchers take advantage of easy-to-guess fetch patterns. I have a hard time differentiating this work from being a prefetch unit with significant compiler hints, microarch support, and cache integration. Maybe that's what it is... but if that's the case, I'm suprised that other work hasn't already done this.

The authors present an analysis of common memory-access patterns. Then, they present their prefetch unit which can be configured by miroarch extensions and accessed in new ways by the core (through specialized registers). They also discuss how the cache being agnostic to prefetch behavior can result in unnecessary cache evictions. By making the cache prefetch-aware, they reduce unnecessary cache evictions.

Hot takes:
personal interest: 6/10       (deep learning workloads have highly predictable memory-access patterns)
paper quality / novelty: 8/10 (seems like a v. solid paper to me, I'm just not clear on how this is substantially different from existing prefetechers. Seems like a bunch of well-done engineering work).
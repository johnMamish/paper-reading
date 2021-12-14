Batteryless systems comprising many batteryless nodes that communicate with each other hold promise, however, they also come with engineering challenges that are difficult to model. The nodes in the system may harvest drastically different amounts of power at different times, and they may all simultaneously be affected by one event.

To enable the development of systems comprising many batteryless nodes, a test platform is needed that can replay Ekho-style energy harvesting traces to many nodes simultaneously. The authors introduce Shepherd, a system that can power individual batteryless platforms with energy-harvesting traces much like Ekho, but which introduces support for playing back many traces in parallel, time-synchronized with a precision of a few microseconds.

The authors achieve this by having a dedicated "Beaglebone black" SBC for each batteryless node which synchronizes its time with other nodes using existing, proven tooling (e.g GPS, IEEE 1588). Each BBB (Beaglebone black) can capture or play back a trace like Ehko.

Hot takes:
personal interest: 8/10 (seems like a critically important tool for batteryless work in the next few years, if these guys did it well)
paper quality / novelty: 8/10
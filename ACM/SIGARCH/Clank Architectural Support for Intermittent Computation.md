## Clank: Architectural Support for Intermittent Computation
#### [[Matthew Hicks]], 2017
#### Summary
Software based methods for dealing with intermittency are high-overhead and require a lot of intervention from programmers. The author presents Clank, a set of hardware utilities that doesn't take up much die space and lets programmers achieve intermittent operation with minimal firmware overhead. As described in paragraph 6 of section 1 and section 2, Clank works by determining idempotency-violating reads and writes at runtime; it buffers an arbitrary number of these reads and writes, and once the number is above a threshold, it triggers a small handler routine in firmware which flushes these reads and writes to nonvolatile memory. As buffer size increases, tradeoffs about checkpoint frequency and time change (Section 7); Clank includes a watchdog timer to avoid the situation where - if the threshold is very big because of a huge buffer - backups never occur and forward progress is never made.

Table 1 shows Clank's results, forward execution is guaranteed at a negligble size and performance penalty.

#### Strengths
  * Clear description/writing
  * Lots of experiments

Keywords: #keywords/energy-harvesting #keywords/intermittent-computing #keywords/batteryless #keywords/idempotence
Tags: #tags/favorite 
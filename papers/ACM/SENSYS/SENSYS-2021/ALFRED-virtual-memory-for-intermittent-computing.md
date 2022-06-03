## ALFRED: Virtual Memory for Intermittent Computing
#### [[authors/Andrea Maioli]], [[authors/Luca Mottola]], 2021
#### Summary
Batteryless systems  intermittently lose power, which causes their volatile memory to be wiped. For computation to happen in this environment, variables need to be backed up to nonvolatile memory at opportune times. The authors present ALFRED, a set of compiler passes for intermittent code written in an intermittent task-based or checkpointing paradigm. ALFRED is meant for code that runs on **mixed-volatileily microcntrollers** - those which can quickly write to nonvolatile memory with byte-level granuarity (e.g. MRAM). ALFRED reduces reads and writes to nonvolatile memory in order to save power.

ALFRED starts by inserting naive checkpointing, backing up the entire memory space at each checkpoint. After this, it optimizes code at the IR level through 3 main mechanisms:
 - mapping of write operations: redundant writes to nonvolatile memory are eliminated
 - mapping of read operations: redundant reads from nonvolatile memory are eliminated
 - consolidation of read operations: more redundant reads from NVM are eliminated
The basic treatments of these methods in section 3 only operate on basic blocks. The authors introduce a memory location tagging system to deal with runtime uncertainty that arises with loops. They deal with intermittence anomalies (re-execution of non-idempotent code) by buffering the same variable in 2 different locations (one for writing and one for reading) (section 5.2).

The authors characterize the power required for volatile and nonvolatile operations (on an MSP430FR microcontorller) and use these figures to build a model so they can test their system on an emulator. For most workloads, ALFRED reduces energy consumption by 10 ~ 50% when compared to other methods that automatically checkpoint at compile time. More complex workloads give better improvement.

#### Strengths
  - Doesn't require changes to program
  - Operates on IR level, making it platform independent

#### Weaknesses
  - Eval section super long, but feels like it doesn't say a ton.

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[intermittent-computing]] [[compilers]]
Tags: [[tags/friends]]
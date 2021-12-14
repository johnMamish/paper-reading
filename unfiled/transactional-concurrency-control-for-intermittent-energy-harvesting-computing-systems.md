New programming paradigms have been developed to deal with the loss of state associated with frequent and unexpected power loss in intermittently-powered systems. Most of these paradigms involve defining tasks that are atomic and idempotent, which makes backing up and handling power failures tractable and predictable, but a major drawback to these methods is that interrupts break some basic assumptions that these methods make, so interrupts can't be used. The authors introduce Coati, a runtime library and set of extensions to C that address these issues. Coati works by splitting interrupts into 2 phases. The first phase doesn't affect the consistency of application data structures, so it can interrupt atomic tasks; it's just responsible for handling urgent I/O requirements. The second phase of the interrupt is queued until an atomic task relinquishes control, meaning that it can then alter application data structures.

The authors evalute the effectiveness of Coati by looking at the programming effort (Table 4) and also showing that Coati applications capture as many events as a hand-optimized system but at much lower programming effort (figure 10). They also compre Coati to a somewhat similar approach that makes the effects of interrupts consistent with an intermittent task-based system through buffering; they find that the overhead incurred by buffering significantly impact performance.


Hot takes:
personal interest: 8/10
Related to the core of stuff that Josiah has done.

paper quality / novelty: 7.5/10
results seem impressive and the method seems sound. I question how solid the barrier is between phases 1 and 2 of their proposed interrupt model, but maybe I just didn't read close enough.

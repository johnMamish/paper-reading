Approximate computing is promising for many modern applications like deep learning, data compression, and motion planning. The authors propose a method of approximate computing where functions that would take several hundred cycles to execute have their outputs memoized in a hash table. The inputs to the function are used as the hash keys and the outputs of the function are the hash values. Instead of computing a function for any input values that arrive, if the input values are the exact same as for a previous evaluation of the function that's been stored in the hash table, then the function itself doesn't need to be computed a hash lookup just needs to happen.

They add architectural support for these memoization hash tables. To deal with the fact that functions with different numbers of arguments need to be supported by the same architectural extentions, they hash using a CRC which can handle arbitrary-length inputs. The approximate computing aspect comes in because the authors recommend the rounding of inputs via truncation before computation and hashing. For example, f(6.5) and f(6.75) might be hashed to the same memoized result if you're working in 13q2 fixed point and truncate the LSB.

They also provide compiler support for automatically detecting code blocks that can potentially be memoized.

I think one weak point of this work is that this works best under the assumption that dy/dX is roughly even for the entire function. Truncating input values might introduce no error in some parts of the input space but enormous error in others. The authors obviously know this; I have no way of getting around it that I can think of.

Hot takes:
personal interest: 7/10
paper quality / novelty: 7/10

Research Opportunity: Awesome research opportunities here for edge computing stuff. They do this as a CPU architectural extention, but there's no reason that it couldn't be applied to accelerators.
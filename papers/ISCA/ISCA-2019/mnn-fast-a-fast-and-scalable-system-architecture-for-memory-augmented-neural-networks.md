A new type of neural network, called a "memory-augmented neural network", promises to deliver drastically improved performance for some inference tasks. For reasons that aren't entirely clear to me, memory-augmented NNs have different memory access patterns than DNNs (maybe because of the "embedding"?). The authors propose 3 unrelated(?) techniques for speeding up memory-augmented NNs:
  1. A re-ordering of matrix multiplications to reduce cache thrashing.
  2. Skipping some parts of the output computation. I'm not sold at all that this really does that much to decrease computation overall, but I'm probably just not familiar enough with the math of memory-augmented NNs.
  3. Avoiding caching some values to reduce contention between "embedding" and "inference" operations. AFAICT, they take advantage of knowledge about the orthogonality of "embedding" and "inference" operations to know - at compile time - what things don't need to be cached. For CPUs and GPUs, AFAICT this means using special non-caching instructions to access some data. AFAICT for FPGAs this means adding extra, reserved cache space for different types of operation.

Hot takes:
personal interest: 5/10
paper quality / novelty: 7?/10
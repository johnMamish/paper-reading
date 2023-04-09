## EnerJ: approximate data types for safe and general low-power computation
#### Sampson, Dietl, Fortuna, Gnanapragasam, Ceze, Grossman, 2011
#### Summary
A great deal of power is spent on ensuring the absolute correctness of computations, even when it isn't required. Seperating between places where correctness is absolutely necessary and where it isn't, however, is difficult; calculating an FFT has tolerance to error, but calculating an index into a jump table has no tolerance for error. The authors partition programs into sections that can and can't have error by **annotating variables**.

The authors implement their system by extending Java with 3 main ideas:
 - @Precise: Variables with this annotation cannot be involved in approximate computations
 - @Approx: Variables with this annotation must be involved in approximate computation
 - endorse(approx): Used to convert an approximate variable to a precise one.
Key to EnerJ is the idea that @Approx variables can't be involved in precise computations without the programmer's exact say-so (via endorse()). For this reason, @Approx variables can't be used for flow control. The authors have other extensions for OOP-related design concerns; all can be seen in Table 1.

The authors study the effectiveness of EnerJ by implementing several benchmark programs in EnerJ and then running them on a simulator which simulates errors due to energy saving in memory retention (SRAM untervoltage & DRAM slow refresh), arithmetic timing, and precision reduction. They find that - even in the presence of errors the - the total output error of the programs is acceptable (Figure 5). They also ESTIMATE the power saved by the introduced errors.

EnerJ is a Java extension which enables approximate computing where it's appropriate and precise computing where it's necessary by type annotations.

#### Strengths
  - Annotation scheme provides good guarantees
  - Seems very easy to use
  - Datatype-driven annotations

#### Weaknesses
  - Most power optimizations not compatible with curent architectures
 
#### Additional comments
Their choice to seperate DRAM and SRAM by whether the variable is on the heap or stack is strange.

#### What potential directions of future work remain (if any)?
It would be interesting to see architectural support for these compiler features.

#### Citations


Keywords: [[keywords/programming-languages]], [[low-power]], [[compilers]]
Tags:
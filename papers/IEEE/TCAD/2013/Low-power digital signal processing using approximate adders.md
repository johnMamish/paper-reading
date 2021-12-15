conference TCAD

## Low-Power Digital Signal Processing Using Approximate Adders
#### [[Debabrata Mohapatra]], [[authors/Anand Raghunathan]], [[authors/Kaushik Roy]], 2013
#### Summary
Lossy compression often involves adding quantization error to the results of transforms; this means precise computation isn't essential for some parts of lossy compression. Armed with this observation, the authors construct 5 different approximate adders and multipliers which they use to implement DCT and FIR filter circuits. The authors use these circuits and others to perform JPEG and MPEG compression.

The authors introduce 5 different approximate one-bit full-adder circuits, all based off of the classic mirror adder design. The adders are designed to take less power because they have less node capacitance, fewer devices, and lower propagation delay (so a lower supply voltage can be used). The alternate adder designs introduce bit-errors in 12.5 - 37.5% of the full-adder truth table, depending on which design is selected. In multi-bit adders, the authors only use their approximate adders for the least-significant bits; they simulate image compression error and power consumption for replacing the 7 - 9 LSBs with approximate adders (fig 9, 10).

#### Strengths
  - Takes advantage of an unusual property of the calculations in lossy compression - they don't need to be bit-accurate (this isn't true for, say, constructing a hash table).
  - Results in significant power savings.
  - Authors characterize their improvements in 3 pretty big applications: image compression, video compression, and FIR filtering.
  - Differs from other approaches which usually rely on undervolting - their computations are still deterministic, they're just wrong.

#### Weaknesses
 - No discussion about dynamically changing between accurate and approximate hardware; might be nice.
 - Test output image (Fig. 8, far right) looks noticably worse.

#### Additional comments
I'm interested about whether there's a good way to dynamically change the inaccuracy. An obvious solution would be to have some of the approximate circuits in parallel with accurate ones and power-gate them, but maybe there'd be a different way. FWIW, "a different way" would probably be inamenable to the technique introduced here.

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - [[Highly energy and performance efficient embedded computing through approximately ... experimental validation]] Described in this paper as "nonuniform Voltage Overscaling". Maybe similar to an idea I've had in the past?

Keywords: [[approximate-computing]], [[compression]], [[low-power]], [[vlsi]]
Tags: [[favorite]]
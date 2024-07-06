#### Thurein Paing, Jason Shin, Regan Zane, and Zoya Popovic, 2008
#### Summary
To harvest maximum energy from rectennas (rectified antennas), a switching regulator must operate at the maximum power point. However, the control circuitry to achieve this often consumes more power than is harvested. This work presents a highly efficient boost regulator control circuit which appears to the input as a roughly constant value resistor and to the output as a bursty current source.
The authors use a key insight: if the regulator stays in DCM mode and has good input filtering, they just need to operate the inductor at a fixed duty cycle to achieve a fixed resistor emulation. This yields a control circuit buildable with discrete components whose extremely low power consumption can be attributed to its open-loop operation. They characterize its inefficiencies and describe its principle of operation. They harvest energy from a rectenna at 85-90% efficiency to show its viability as a harvester.
This work is extremely relevant to my own research. Its implementation from discrete analog components is very appealing. I'm interested in seeing how the circuit can be designed to work with variable resistances and how it can be cold-booted from 10s of mV. I'm also interested in seeing how its power consumption can be reduced.

#### Strengths
  - Very simple and elegant core idea gives excellent results
  - Use of off-the-shelf discrete components makes study easy to replicate

#### Weaknesses
  - Efficiency of control circuit middling. I imagine this could've been done better.
  - Explanation of circuit operating principle could've been done better. I would've had more discussion about the ripple voltage.
  - I also think maybe they miss the point of why the ripple capacitor is so important... the real issue is that the error in the emulated resistance can't be figured out by just the error... it's RMS.
  - A discussion of active control would've been great. They do give a citation for looking at this, but I would've liked to see some discussion in the paper.

#### What potential directions of future work remain (if any)?
I'm extremely interested in using this with MFC harvesting and in applying it to other, similar harvesting work.
I think that a lot of the analog control circuitry could be replaced by digital circuitry.

Some potentially different parts to use for PWM generation: TS3001

#### Citations
Some comments about the citations
 - [[Resistor Emulation Approach to Low-Power Energy Harvesting]]
   Resistor Emulation for... RF Energy Harvesting is essentially an adaptation of this cited work. This work discusses closed-loop methods for more accurately emulating resistance.
 - [[Adaptive Piezoelectric Energy Harvesting Circuit for Wireless Remote Power Supply]]
 - [[Buck-Boost Converter for Sensorless Power Optimization of Piezoelectric Energy Harvester]]

Keywords: (link to pages under the keywords/ directory here)
Tags: (link to pages under the tags/ directory here)
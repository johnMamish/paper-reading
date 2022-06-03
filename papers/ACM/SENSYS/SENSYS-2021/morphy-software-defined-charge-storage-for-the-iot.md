## Morphy: Software-Defined Charge Storage for the IoT
#### [[authors/Fan Yang]], [[authors/Ashok Samraj Thangarajan]], [[authors/Sam Michiels]], [[authors/Wouter Joosen]], [[authors/Danny Hughes]], 2021
#### Summary
Because there is so little of it to go around, energy management in batteryless systems is paramount. The required characteristics of a harvesting / storage capacitor might change depending on task load and harvesting conditions.

To this end, the authors introduce Morphy, a hardware module with some associated OS-level software primitives. Morphy's hardware consists of an array of capacitors (16 x 100mF in their implementation), linked together by an array of ADG824 analog switches. This topology allows these capacitors to be reconfigured on-the-fly as, say, one giant 1600mF capacitor or as four seperate 400mF capacitors, each one dedicated to a specific task. Moreover, Morphy can be reconfigured as charging occurs to maximize charging rate (more on this later). Morphy's software interface consists of two new primitives: an "energy semaphre" (which associates a certain fraction of the energy budget with a certain software task (a-la [[Josiah Hester]]'s UFoP)) and an "energy watchdog", which lets the OS police tasks which violate their claimed energy budget.

The authors implement Morphy as a physical circuit board and its software primitives as FreeRTOS plugins. They simulate a solar power source using a Keysight programmable power supply and build an intermittent system that's comparable to Morphy using methods similar to [[Josiah Hester]]'s [[tragedy-of-the-coulombs-federating-energy-storage-for-tiny-intermittently-powered-sensors|UFoP]], which is similar to Morphy in principle but less flexible at runtime. They find that for their energy harvesting regime, Morphy achieves significantly greater uptime than UFoP.

This paper describes a system that improves upon well-recieved past work by adding flexibility.

#### Strengths
  - Builds well upon previous work
  - I find the systems element really appealing
  - Built actual hardware
  - Nice graphs in Figure 12

#### Weaknesses
  - Not entirely clear to me how their software primitives help Morphy work better. Maybe they're just a necessary compatibility layer.
  - I dislike their charge pump argument. I think it's a half-baked pot-shot at a deeper, more general idea. 

#### Additional comments
  - Morphy as a way to improve energy harvesting efficiency at low voltages
    The authors tout Morphy's ability to act as a charge pump, saying that it can improve energy harvesting efficiency. I believe that - while this is true - it barks up the wrong tree. There should be a much more efficient solution based on some sort of impedance matching regulator, of which Morphy could be a component at the output stage.

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - Heavily based off of [[Josiah Hester]]'s [[tragedy-of-the-coulombs-federating-energy-storage-for-tiny-intermittently-powered-sensors|UFoP]].

Keywords: [[batteryless]], [[energy-harvesting]]
Tags: 
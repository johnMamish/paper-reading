## An Analog Front-End ASIC for Cardiac Electrical Impedance Tomography
#### Rao, Odame, et. al, 2018
#### Summary
One of the most compelling traits of EIT is its POTENTIAL for portability and unobtrusiveness, making detailed measurements much easier to take. Extant EIT systems are extremely bulky and make deployment hard, meaning that critical diagnostic info might be missed. The authors of this work design, fabricate, and test an analog ASIC which contains all of the major analog components needed to conduct EIT.

The authors create a chip which contains a current driver, a differential and variable-gain amplifier, and a 10b SAR ADC. The chip can be configured to be a current driver or an ADC with amplifier, but apparently not both, which suggests that a full EIT system would require two of their ASICs. The ASIC components are as follows
 - A current driver - the design is based off of a CCII current conveyor and due to a class AB buffer at the output has high output impedance to ensure high accuracy. Linearity is ensured by using a resistor to V-to-I conversion. The amplifier has low harmonic distortion.
 - A 10b SAR ADC - a SAR architecture is used to limit power consumption. Minimum sampling rate is determined to be ~40ksps via equation (1), but the authors choose a sampling rate of 250ksps. The ADC consumes ~77uA at 3.3V.
 - Voltage sensing amplifiers - A chain of two amplifiers is used which together offer up to 36V/V amplification.

Note the absence of an integrated waveform generator.

The authors measure system SNR of their chip, make a Cole-Cole plot of SNR when measuring a parallel RC load, and compare their measured values to theoretical values, showing good agreement. They determine the maximum frame rate of their system to be **21 fps** with a 32 electrode system. In table 4, they compare the performance of their system to other similar ASICs.

Overall, this paper is an excellent cookbook for analog front-end design for EIT systems.

#### Strengths
  - In depth discussion of implementation details & design choices
  - Actual chip fabbed

#### Weaknesses
  - Chip DOESN'T get used in an actual EIT system, just characterized in an ideal benchtop envrionment. Just an analog design exercise that's targetted for EIT.
  - Novelty is questionable.
  - Integration suffers - many other parts will still be needed for a complete EIT system.

#### Additional comments
Great reference for analog design considerations in an EIT system

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords:  [[keywords/electrical-impedance-tomography]], [[analog]]
Tags: 
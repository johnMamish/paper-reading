conference IEEE/ISSCC

## An ultra-low-energy multi-standard JPEG co-processor in 65 nm CMOS with sub-near threshold supply voltage
#### [[authors/Yu Pu]], [[authors/Jose Pineda de Gyvez]], [[authors/Henk Corporaal]], [[authors/Yajun Ha]], 2009

#### Summary
The authors use sub-threshold logic to implement a JPEG compression engine. To avoid process-variation related issues with sub-threshold logic, they add a threshold imbalance detector circuit which actively adjusts the body bias of the high- and low- side transistors to make sure they're evenly matched. They also observe that a simple geometry change in the transistors - using many narrow strips instead of one thick one - improves current driving capability. Performing voltage scaling by decreasing the operating frequency of a circuit gives superlinear power savings - especially when the circuit is sub-threshold (if you double the size of a circuit but halve its clock frequency to achieve the same throughput, you'll save power). To this end, the authors use many parallel subtreshold circuits for the easily parallelizable DCT and quantization operations. The sub-threshold circuits are in a seperate clock and voltage domain from higher frequency circuits which need to do serial operations (differential coding of DC values, huffman coding).

The authors have actually fabricated and tested a chip. They provide micrographs. They characterize the pJ / operation at a range of operating voltages.



#### Strengths
  - Application of classic sub-threshold architecture-level techniques (highly parallel, lower clock freq, lower voltage).
  - No special fabrication techniques are needed 

#### Weaknesses
 - This is a symptom of the conference, but their experimental section lacks a lot of detail (what is an "operation", how much power do some other similar works consume, how many "operations" are done per second / what is the bottom line of power consumption?)
 - Some extra work to integrate with a larger SoC might be required?

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?

Keywords: [[keywords/sub-threshold-computing]] [[jpeg]] [[dsp]] [[keywords/architecture]] [[keywords/voltage-scaling]]
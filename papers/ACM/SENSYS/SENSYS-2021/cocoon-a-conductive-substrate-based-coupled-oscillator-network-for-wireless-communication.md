## COCOON - A Conductive Substrate-based Coupled Oscillator Network for Wireless Communication
#### [[authors/Xingda Chen]], [[authors/Deepak Ganesan]], [[authors/Jeremy Gummeson]], [[authors/Mohammad Rostami]], 2021
#### Summary
Synchronization between wireless RF nodes can drastically improve their performanice, however, achieving the best synchronization possible relies on very expensive and power-hungry temperature-compensated oscillators. Finding cheaper and lower-power ways to provide precise clocks to distributed systems would improve performance across a variety of applications, like warehouse inventory tracking, indoor localization, data center monitoring, and beamforming.

The authors take advantage of the well-known phenomenon whereby oscillators with different natural frequencies will synchronize if they are coupled. They use a cheap conductive substrate (like paint or paper) to couple together many cheap nodes with low-precision oscillators. To improve system performance, they also include a high-cost high-power base station which injects a precise frequency into the substrate. By looking at the frequency content of the substrate (?), the base station can determine lock quality.

The authors deploy many RF nodes equipped with ceramic oscillators onto 3 different types of conductive substrate (not sure where / how they were coupled). They carry out several experiments
 - They measure the mutual coupling between the ceramic oscillators without the substrate being driven by a high-precision base station
 - They attach a high precision oscillator to the substrate and measure frequency locking
 - They check to see how well the base station can detect locking (and "quasi"-locking)
 - They characterize the amount of power that the base station needs to expend to keep the nodes locked

The authors find that synchronization occurs at frequency differences larger than the tolerance of low-cost ceramic oscillators or ring oscillators, and at large substrate resistances (figure 5; knee in graph represents loss of lock).

While this work is limited in its deployability, it can significantly improve the scalability of distributed wireless systems in restricted environments.

#### Strengths
  - Method is cheap and effective
  - Principle is well-explained
  - Very solid / exhaustive experimental section

#### Weaknesses
  - I'd like to see more of a discussion on how the coupling occurs. Do you just short a node of the Colpitts oscillator to the wallpaper??
  - Method is severely limited in its deployability

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?

#### Citations
Keywords: [[wireless-communication]], [[keywords/wireless-sensor-networks]]
Tags: 
## RF Soil Moisture Sensing via Radar Backscatter Tags
#### [[Colleen Josephson]], Bradley Barnhart, [[Sachin Katti]], Keith Winstein, Ranveer Chandra, 2019

#### Summary
A lot of times, farms over- water their crops, which both reduces crop yield and takes unnecessary money. It's widely known that soil moisture sensors alleviate this issue, however, commodity soil moisture sensors are expensive, hard to deploy and maintain, and hard to collect data from. Using Time-Domain-Reflectometry, it's possible to determine soil moisture by looking at the ToF of a known signal launched into the ground; typically sensors in contact with the soil are used for this, but if there's a reflector at a known depth, the ToF can be measured by ground-penetrating radar (sections 2.{2,3}). Unfortunately, natural reflectors in soil are dense and randomly distributed, making it difficult to tell a known reflector apart from background noise (Section 3.2.1).

The authors' key insight is the use of a backscatter tag to overcome this "reflector discrimination" problem. They put backscatter tags in the ground which turn their antennas on and off in such a way that they appear to have a doppler shift. This allows the ground-penetrating radar to discriminate specific tags from the background and from each other. They also include an actively powered tag that can work at lower depths than the backscatter tag.

The system devised by the authors is an order of magnitude cheaper than other systems, but it still achieves roughly the same accuracy. Furthermore, because the tags are backscatter, they have an exceptionally long battery life, making deployment and maintenance easier. The authors outline interesting future directions in section 8; they suggest many improvements to a fundamentally useful system.

#### Strengths
 * Discussed in the paper; system is cheaper and easier to deploy/maintain than existing solutions while maintaining performance parity
 * Future work directions are interesting and strong
 * High impact

#### Weaknesses
 * Maybe it's addressed in the paper, but it seems like it will still be very time consuming to collect data from all the tags.

#### Additional Comments
The method is counter-intuitive. The backscatter tags don't actually do any measurement, they act as passive markers at a known reference point. This is described in the 3rd-to-last paragraph of section 1.

Keywords: [[backscatter]] [[keywords/low-power]] [[keywords/intermittent-computing]] [[conservancy]]
Tags:
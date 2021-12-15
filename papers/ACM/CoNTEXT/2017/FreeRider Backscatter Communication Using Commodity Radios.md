## FreeRider: Backscatter Communication Using Commodity Radios
#### Pengyu Zhang, [[Colleen Josephson]], Dinesh Bharadia, Sachin Katti, 2017

#### Summary
Backscatter is a promising technique for drastically reducing the amount of power that radio nodes take. Unfortunately, backscatter usually necessitiates the use of dedicated hardware to generate the signals that are to be scattered. This hampers consumer adoption because extra hardware will need to be purchased or designed into products and because the extra signals pollute precious consumer RF bands. In previous work by the same authors - HitchHike - backscatter radios are excited by valid packets from commodity radios, and they communicate by transforming those packets into other valid packets through backscatter techniques. This work further extends HitchHike, adapting its techniques to operate with a broader class of commodity radios. They also introduce a method for receiving control information passively from commodity radios using a backscatter receiver that only requires COTS RF components.

The authors show that their system can TX information up to ~25 meters. They also show that - when using zigbee or bluetooth channels for communication - their system can operate at the same time as WiFi is operating. For their system to co-exist with WiFi, they need to use RTS/CTS flow control. As state above, their system uses only off-the-shelf components and critically does not require a WiFi decoder on the backscatter tag, which would require a prohibitive amount of power. This work is important because it has the potential to move backscatter radios from a lab curiosity to a practically useful real-world technique. I'm interested in seeing how this work can be extended to transmit more data to the tags as well instead of just data coming from the tags.

#### Strengths
 * Actual hardware was built
 * Hardware uses only COTS hardware
 * Open-sourced

#### Weaknesses
 * IDK, this is a pretty great paper

Keywords: [[backscatter]] [[keywords/wifi]] [[keywords/zigbee]] [[keywords/wireless]]
Tags: [[tags/favorite]] 
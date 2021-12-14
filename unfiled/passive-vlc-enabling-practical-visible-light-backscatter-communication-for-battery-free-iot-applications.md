Some batteryless systems have had success in communicating by using the power imparted by the physical layer of the communication stack to harvest energy; RFID tags have been doing this for a long time, and backscatter techniques do something similar, but in addition they take advantage of the carrier transmitted by a battery-power device to encode data - they don't generate a carrier wave of their own.

This paper introduces improvements to the visible light version of this idea. Previous work has been done on this, but the authors provide a few new techniques to optimize it and they provide further analysis. The authors present a batteryless transmitter (kinda like an RFID tag) which consists of a solar panel to harvest energy and a transmission unit which consists of a retroreflective surface covered by an LCD-based shutter. The transmitter can be read by pointing a reciever at it consisting of a bright LED. The LED provides power, and the transmitter reflects varying amounts of light back at it depending on its LCD, allowing it to encode information at up to 1kbps.

There's some difficulty associated with modulating the LCD screen; the authors discuss how they design a coding scheme to overcome these issues with the LCD's responsivity.

They can achieve reliable communication at a distance of up to ~1 meter at a range of angles. They can also achieve a downlink by modulating the powered light source.


Hot takes:
personal interest: 7/10
Very cool idea.

paper quality / novelty: 8/10
They have a thorough and interesting treatment of how they optimize coding and physical layer for the drawbacks of the LCD (section 4). I wish they'd said something about how damn bright the LED that they have to point at the thing is... up to 3 Watts!!
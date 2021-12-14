As RF bands continue to take on new tenants, our communications will have to start finding other places to live. A promising place to occupy is the visible light spectrum, but existing methods come with a few drawbacks: they require control over a light source (which is often intractable in terms of infrastructure), requre an energy-hungry reciever, or are visible to the human eye.

The authors take inspiration from backscatter RF communication and propose Luxlink. Luxlink transmitters reflect ambient light through an LCD cell and use frequency modulation to encode information. Recievers consist of a single photodiode with a polarized filter. The link supports ~80bps at ranges of a few meters, with range improving outdoors in ambient sunlight. As shown in figure 18, the reciever is not very robust to horizontal translation. The orientations of RX and TX are fixed; they point directly at each other when the RX offset is 0 (section 5.3.2).

Future work: I think that there could be something cool here to be said about having a batteryless version of this transmitter. I also wonder if bidirectional communication could be achieved... luxlink relies on sunlight going THROUGH the LCD cell, but I wonder how well it would do with ambient light reflecting OFF of the LCD cell. Certainly SNR would be drastically worse, but maybe that could be overcome in a future work.

Hot takes:
personal interest: 6/10
Another communication method in bag of tricks for batteryless nodes.

paper quality / novelty: 8/10
Clever idea, excellent development and analysis, questionable impactfulness.

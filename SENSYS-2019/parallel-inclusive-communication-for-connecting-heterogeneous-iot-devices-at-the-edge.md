There's a growing need for WiFi and BLE devices to coexist, but their bands overlap, leading to dropped packets which increases delay and power consumption. The authors of this paper introduce a method for overcoming this issue when working in a star-topology with a single base station that needs to communicate with both WiFi and BLE devices. The uplink and downlink problems are handled seperately. For downlink, the base station embeds BLE frames in valid WiFi transmissions, eliminating collisions in downlink (Section 3.3). For uplink, the base station oversamples, which allows it to de-conflict the signals (Section 4). The authors test their system by implementing it with an SDR.

Hot takes:
personal interest: 4.5/10
I think the RF stuff is cool, but I don't know how applicable this is to my own research.

paper quality / novelty: 7/10

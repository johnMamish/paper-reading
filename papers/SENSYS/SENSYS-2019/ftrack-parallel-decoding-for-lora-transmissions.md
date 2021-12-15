LoRa is an emerging RF communication protocol / PHY for LP-WANs; as the number of nodes increases, MAC management will become untenable. Existing work to alleviate this problem has proposed to just allow packets to collide and let the reciever deal with de-colliding the packets by taking advantage of each LoRa node's frequency offset (?), but this method is unscalable. The authors propose a DSP-based technique that de-collides misaligned symbols by taking advantange of LoRa's chirp-based PHY. Figure 1 shows very clearly how this is really quite tractable. They have a discussion section about the minimum amount of computation needed to de-collide packets (3.5).

Hot takes:
personal interest: 7/10
If unidirectional batteryless nodes don't have to worry about MAC, you can save a ton of power(?). It looks like this method doesn't ask the TX-er to do any extra labor.

paper quality / novelty: 7.5/10
Kinda obvious idea, it appears that they may have a good discussion around computation budget, but I worry that the amount of FFT you'd have to do / sample rate makes this method intractable for really low power recievers.
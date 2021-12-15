Inventory tracking is big business in the US and China, but existing solutions leave something to be desired: barcodes slow the flow of inventory processing because they need to be in line-of-sight, RFID tags are expensive and environmentally unfriendly. The authors introduce an inventory tag comprising a unique pattern printed in ferrofluid. The tag can be read by blasting it with mmWave radiation and looking at the frequency distribution of the reflected energy; small variations in the shape of the tag will change its frequency response. Tags printed with ferrofluidic ink are extremely cheap and easy to make (existing printers can easily be retrofitted) and are more biodegradable than barcodes.

Hot takes:
personal interest: 3/10
These guys are gonna make a lot of $$$ with this, but nothing that relevant to my research.

paper quality / novelty: 7/10
Very cool idea, but the experimental coverage left a lot to be desired after the promises they painted in their intro.

I found a major shortcoming of this paper to be lack of a discussion about decoding similar tags under different ambient conditions (occlusion, angle, distance, etc). They briefly address this in figures 22 and 23, but what happens if you blast 3 boxes with varying contents (books, electronics, food) with the ferrotag reader? How is it possible that the contents won't drastically affect the readings to a point where the tags can't be differentiated? Of course, you could characterize the transfer functions of the boxes with their contents.... but that's intractable for practical deployments.
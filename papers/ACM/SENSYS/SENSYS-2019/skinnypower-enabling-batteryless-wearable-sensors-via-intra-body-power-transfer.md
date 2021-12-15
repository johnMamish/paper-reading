Body-Area-Networks are promising for medical applications, but their potential is hampered by the reliance of individual sensor nodes on batteries. Batteries increase the size of sensor nodes, they need to be replaced (which decreases user adoption and is bad for the envrionment), and limit the application of novel technologies like sensors embedded in the body or tattoo-based sensors. If we could transmit power through the body, users could wear a single battery somewhere on their body and many sensors could be powered by that one battery, allowing platforms to expand the number of devices in their BAN without increasing the number of batteries. Transmitting power through the body is challenging because there's no way to seperate the body into a power transmit and return path. Existing methods use galvanic coupling, which can't transmit power very far through the body (Figure 2.c/d) because of this lack of separation.


The authors propose a method for transmitting power that relies on capacitive coupling through earth ground. Because the parasitic capacitance to earth ground is so small, for this method to be useful, power has to be transmitted in the 100s of MHz.

The authors demonstrate that their system can deliver ~1mW to devices ~20-30cm from the transmitter on the human body. They show that different gestures and body motions don't compromise their system's ability to transmit power (there's some variation, but not too much.). I wonder how their system is affected by coupling to earth ground in different envrionments (e.g. outdoors, on a metal floor, etc).

Very cool idea, but the experimental evidence is very underwhelming.

Hot takes:
personal interest: 8/10 (could be super valuable for one of Nabil's things.)
paper quality / novelty: 6/10 (an idea that needed to be tried, but the experimental stuff (the real meat of the paper IMO) leaves a lot to be desired. They do get some bonus points for having great diagrams and explanations).
Using phase information to locate RFID tags is a classic technique; past work has used phase information of recieved RFID signals to construct a 2d heat map of likely tag positions called a "hologram". The authors present a new formula for constructing these "holograms" which they claim has slightly better performance, but which I can't really judge (Section 3.2). The authors also feed these 2d heat maps into a CNN as if they are a 2d picture to try and combat false maxima caused by multipath effects.

Hot takes:
personal interest: 4/10
Cool paper... batteryless indoor localization in the face of multipath and arbitrary occlusions is a very "futuristic" "jetsons" type problem. This just doesn't really apply to me.

paper quality / novelty: 7.5/10
These guys have the whole "slap a CNN on it and see if it does better"-itus problem, but... in this case... it really DOES do better... and it's an interesting problem. At least they have their new hologram generation method (which fwiw doesn't seem to do much).
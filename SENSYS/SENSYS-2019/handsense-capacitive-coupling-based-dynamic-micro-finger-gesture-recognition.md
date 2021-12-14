For AR systems to become useful in a wider range of environments (industrial, medical, etc), they need a user-friendly and reliable input method. Input methods now typically rely on the use of a smartphone, which is infeasible for target applications where the user needs their hands, or the use of a camera to identify hand position, which requires users to keep their hands visible in a certain area and requires a lot of compute. The authors of this paper present a user input modality targetted at AR systems (but which could work for other systems) that consists of a glove outfitted with capacitive touch sensors at the fingertips. Using capacitive coupling between the fingertips on a hand, they can identify up to 14 different hand gestures (Figure 7). To avoid interference from capacitive coupling with the human body, they have a dual-electrode structure (Figure 3). After capacitive measurements have been gotten by the glove, they are offloaded to a compute unit which classifies gestures with an LSTM; confusion matrices look pretty damn good and can be found in Figure 10. Power consumption is horrendously high, but it looks like they've made no effort so far to decrease it.

Hot takes:
personal interest: 6/10
Making something like this batteryless could be awesome.

paper quality / novelty: 7/10
Their platform still seems unwieldy, but I like the idea and execution a lot. Maybe this is just slapping a neural network on shitty data... but I don't think so. The confusion matricies are too good.

I wonder how much the ambient environment affects readings. They don't address this at all... what if you're close to a piece of metal??

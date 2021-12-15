Augmented reality (AR) systems are often power-constrained because their users want to be mobile; this limits the power budget of object tracking, a key enabling operation of AR. Typically object tracking is done by running each camera frame through a DNN (the authors assert this; I'm not so sure).

The authors propose a method where a DNN is occasionally used to detect objects in some frames. After that, a lighter weight, optical flow based algorithm (Lucas-Kanade, see 3.3) is used for following frames. Once the scene changes significantly enough or confidence falls, the DNN is run again on a frame. This method gives about a 50% energy reduction (Figure 6) compared to continuously running a DNN. I couldn't tell very much from this reading how much accuracy is affected. I'd have to read more carefully to figure that out.

Hot takes:
personal interest: 5.5/10 (Not really interested in this particular idea or application, but it does bear some striking resemblances to FFNet... Maybe this could even motivate a small change in form to FFNet where - instead of fastforwarding - we switch to a much lower-accuracy interest-detection method).
paper quality / novelty: 6.5/10
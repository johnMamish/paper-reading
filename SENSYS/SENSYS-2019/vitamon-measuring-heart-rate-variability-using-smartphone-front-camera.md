Measuring the time difference between peaks in someone's ECG is an important physiological marker, however, methods that collect this data have 2 main drawbacks (intro. paragraph 2): required equipment is uncommon, inaccessable, and expensive; and methods typically rely on direct skin contact, which is cumbersome.

The authors present a method for extracting heart rate and heart rate variability from video of a subject's face taken with a commodity smart phone camera. They can extract heart information from the face because the human face shows very slight color variation as blood pressure changes due to heart activity (esp in the green channel). Their method is robust to low resolution and low frame-rate; this is challenging because a sample rate of 15 samp / sec of an ECG would limit accuracy of heart rate frequency detection. The authors get around this with the key insight that different parts of the face have different phase shifts because of the propagation delay of blood.

They train a CNN to look at 25 vertically stacked frames of the green channel of a subject's face. They are able to get about 15 milliseconds of precision.

Hot takes:
personal interest: 4/10
paper quality / novelty: 8/10 (maybe i'm too easily impressed; this is the first sensys paper I'm looking at).
Due to economic forces, mobile platforms vary widely across users; moreover, the ways that users interact with these platforms varies widely. E.g. one camera might have drastically different color sensitivity levels than another, and one user might hold their camera in a different way; in spite of this, we still want a single DNN model to work on data recorded by a wide variety of platforms.

Of course, one could train a seperate DNN model for each available platform, but this is infeasible. The authors present a method to tweak existing DNN models to work on platforms given only a few pieces of labelled data. This way, a DNN can be trained on a limited number of platforms, but then with only a few (1 - 10) labelled samples of data from a new platform, the DNN can be adapted to that platform. They evaluated this with accelerometer data and microphone data.

TRANSFER LEARNING is a related technique.

Hot takes:
personal interest: 7/10
I'm always worried about how a DNN trained on grayscale CIFAR-10 data will do with a camera like the hm01b0. This paper addresses those sorts of concerns. I didn't have time to fully suss out HOW they do it, but I just need to remember that this method - and a cluster of related methods - exist.

paper quality / novelty: 7??/10
I didn't have time to understand how they did what they claimed to do.
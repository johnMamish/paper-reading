Exploiting sparsity in neural networks is a well-researched technique when it comes to digital DNN accelerators, however, because emerging analog compute-in-memory NN accelerators can operate in a crossbar structure, sparsity hasn't been looked at yet closely for analog DNN accelerators. The authors claim that the assumptions that support this lack of research are wrong; because of analog inaccuracies (Section 3 / Figure 5), all of the word lines in an analog NN accelerator can't be activated simultaneously, so there is still reason to take advantage of sparsity in analog DNN accelerators.

The authors propose a few techniques for taking advantage of sparsity (section 4) in crossbar-based analog DNN accelerators.

Hot takes:
personal interest: 6/10
paper quality / novelty: 7.5/10
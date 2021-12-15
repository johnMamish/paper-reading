It's recently been shown that if an attacker can get their hands on a DNN, they can craft harmful counterexamples (e.g. making a DNN misrecognize a stop sign as a speed limit sign with careful placement of inconspicuous stickers). The authors propose a method for generating and maintaining a "quasi-secret" ensemble of DNN models which, together, make attacks of this nature far less tractable. AFAICT, the system that relies on the DNN will make copies of its network that have been randomly perturbed a small amount, and it retrains them on some training examples.

I didn't fully understand how they propose to perturb and retrain the models, and I'm suspicious of this method; how can they be sure that the perturbed DNNs land far enough away from the original one to not be subject to the same adversarial counterexamples? To be fair, they could very well address this issue in the paper, I just might've missed it.

Hot takes:
personal interest: 5/10
Good method for anyone working with DNNs to be aware of.

paper quality / novelty: 7/10
Idea felt novel, but like I said, I'm not 100% convinced that it works great.

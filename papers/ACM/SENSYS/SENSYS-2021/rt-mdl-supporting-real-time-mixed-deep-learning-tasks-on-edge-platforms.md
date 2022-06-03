## RT-mDL: Supporting Real-Time Mixed Deep Learning Tasks on Edge Platforms
#### [[authors/Neiwen Ling]], [[authors/Kai Wang]], [[authors/Yuze He]], [[authors/Guoliang Xing]], [[authors/Daqi Xie]], 2021
#### Summary
Real-time scheduling in edge systems is a well-understood engineering problem; some tasks need to be executed by a certain deadline, so special scheduling algorithms have been designed to make sure that those deadlines are met. Scheduling Deep Learning tasks with hard real-time deadlines introduces 2 new dimensions which can be optimized.
 1. Accuracy can be traded off on-the-fly for latency via network compression
 2. Some portions of the task will be executed on the CPU, and some on the GPU / accelerator

The authors design and implement a system which takes these new parameters into account, scaling classifier accuracy on the fly to meet more deadlines. Their system generates many different models with varying compression for each classifier (multi-level model variants); they then formulate the selection of these models as a weighted multi-objective-optimization problem, where model accuracy must be maximized while deadlines are still met. They also improve hardware utilization by dividing each task into CPU- and GPU- based sub-tasks.

They run several experiments on a 1/10th scale autonomous driving testbed, which must detect traffic lights and classify road signs. Scheduling classifier workloads with RT-mDL drastically improves road sign and traffic light detection accuracy. They also check the viability of their model scaling techniques, showing that they effective shrink the models with only a moderate reduction in classifier accuracy.

When scheduling deep learning classifiers on real-time systems, several extra knobs are exposed that can give better system performance when tuned properly. This work is a good exploration of that idea. 

#### Strengths
  - Poses scheduling problem nicely as an optimization problem
  - Exposes significant opportunities for improvement over state-of-the-art when new assumptions are introduced about a specialized workload

#### Weaknesses
  - Experiment using tiny RC car was cute, but felt unnecessary. I believe that experimental effort would have been better expended elsewhere.

#### Additional comments
This paper has some passing similarities to [[Zygarde Time-Sensitive On-Device Deep Inference and Adaptation on intermittently powered systems]] by Friend-of-the-Lab [[Bashima Islam]]. Zygarde differs in that it uses a different, more reactive method for reducing network accuracy and that it uses energy as a bound, not computation deadlines.

#### What potential directions of future work remain (if any)?

#### Citations

Keywords: [[deep-learning]], [[keywords/scheduling]], [[keywords/autonomous-driving]]
Tags: 
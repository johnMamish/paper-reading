## NELoRa: Towards Ultra Low SNR LoRa communction with neural enhanced demodulation
#### [[authors/Chenninig Li]], [[authors/Hanqing Guo]], [[authors/Shuai Tong]], [[authors/Li Xiao]], [[authors/Jiliang Wang]], [[authors/Yunhao Liu]], et. al, 2021
#### Summary
LoRa is a communication scheme widely used in low-power nodes. LoRa links are typically dynamically adjusted to be as low SNR as possible so as to save power; if a lower SNR is tolerable, less energy will be used in the communication. This paper improves base station LoRa decoding, meaning that edge nodes can use a lower transmit power, saving energy and improving transmission.

The authors introduce two DNNs which act together as a LoRa decoder, outperforming traditional DSP-based methods. The first DNN takes a dual frequency/phase spectrogram as input and filters noise out of it, outputting another spectrogram. This DNN uses LoRa's limited symbol space to try and distinguish signal from noise. The second DNN takes as input a noise-filtered dual histogram and classifies symbols. The DNNs are trained on completely clean datasets collected from commodity LoRa hardware which are augmented with Gaussian noise. For these DNN methods to work, the spectograms need to be time-aligned; the authors use traditional DSP methods to align them using the preamble.

The authors carry out several experiments
 - They characterize the runtime of the DNNs on the base stations
 - They show that using their neural decoder increases tolerance to poor SNR, even with different LoRa settings
 - They show the impact of each of their two DNNs on the symbol error rate as a function of SNR. The filtering DNN improves decoder tolerance to SNR the most.
 - They deploy their system on a campus, compaing the symbol error rate of their system with a baseline. They retrain their system using collected data and show the new symbol error rate.

This is a good variation on a common theme. It's easy to deploy. I'm interested in seeing how this can be improved with in-situ training and learning on the edge nodes.

#### Strengths
  - Practical real-world gain with simple addition to system; single s/w component needs to be switched out
  - Only requires changes to base station
  - Experiments are well executed and convincing

#### Weaknesses
  - Could have explored in-situ retraining
  - Suspiciously weak data augmentation strategies

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?
 - would a different data augmentation strategy work better?
 - If the system does more learning with in-situ data, can it adapt to envrionments in a good way?
 - If we can run similar DNNs on the edge, can we get a better than sum-of-parts improvement?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[wireless-communication]], [[deep-learning]], [[keywords/wireless-sensor-networks]]
Tags: [[tags/best-paper-award]]
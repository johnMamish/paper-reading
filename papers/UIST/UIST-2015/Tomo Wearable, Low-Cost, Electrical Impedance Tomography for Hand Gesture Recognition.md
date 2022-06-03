## Tomo: Wearable, Low-Cost, Electrical Impedance Tomography for Hand Gesture Recognition
#### [[Yang Zhang]], [[authors/Chris Harrison]], 2015
#### Summary
The authors introduce Tomo, a mobile wrist/arm-band which uses electrical impedance tomography (EIT) to make a map of electrical resistance of a cross-section of the user's arm. Because tissue resistance is related to muscle actuation, a classifier can look at the cross-section and estimate which of several gestures is being made. For instance, the data collected by Tomo can be used to determine whether the wearer's hand is relaxed or if they are making a "thumbs-up" gesture.

To collect EIT data, 8 electrodes are used. An AD5933 impedance analyzer excites electrodes with a 40kHz signal and measures the signal returning from the sample. 2 ADG1608 analog multiplexers choose which electrodes excite the sample. The DFT of the impedance analyzer measurements is read by an Arduino and transmitted over bluetooth to a laptop. The magnitude of each impedance measurement as well as the difference between all 28 impedance measurements are used by an SVM for gesture classification.

The authors conducted a user study of their system where they conducted 2 phases of data collection; in each phase, they collected 9 sets of training data and 1 set of testing data for each user from both the arm and wrist. Models were tested on data from the same phases, different phases, and between different users. The system achieves 96.6% classification accuracy when tested on data that's from the same collection session it was trained on. The accuracy drops significantly when tested on data for the same user from a different session, and the accuracy drops even more when trained on one user and tested on another. This suggests that - with the current ML model - the system must be calibrated at every use.

This platform shows that - in principle - hand gestures can be determined through electrical impedance tomography. They build and test wearable hardware that could be used for other EIT applications.

#### Strengths
  - Build actual hardware; very replicable
  - Excellent eval section. Experiments are clearly described and there's a pretty thorough data analysis. I like that they show confusion matrices.

#### Weaknesses
  

#### Additional comments
I'm curious about why they didn't test the samples at DC. Is the impedance of the human body lower at AC?

The authors have a follow-up work [[papers/UIST/UIST-2016/advancing-hand-gesture-recognition-with-high-resolution-electrical-impedance-tomography]] which primarily represents an iteration on the hardware design.

#### What potential directions of future work remain (if any)?
 - The classifier feels like an afterthought. This isn't a criticism - I think it's the right choice for this work - however the work could be extended by an improved classifier.

#### Citations
 - Future work by same authors: [[papers/UIST/UIST-2016/advancing-hand-gesture-recognition-with-high-resolution-electrical-impedance-tomography]]

Keywords: [[keywords/electrical-impedance-tomography]], [[keywords/wearables]], [[keywords/HCI]]
Tags:
Using electrical impedance tomography can be used to determine hand gestures by looking at the tissue inside of someone's wrist. In this paper, the authors develop an affordable hardware platform and software stack using COTS devices to achieve this, they characterize their system, and they try to apply it to real hand gestures.

Their system consists of a high-speed DDS chip from Analog Devices which generates a 40KHz sine wave, an analog mux for selecting between electrodes, a high pass filter, and a microcontroller for collecting data which offloads it to a laptop via bluetooth (figure 4). Up to 32 electrodes are sampled. To achieve real-time performance for EIT solving, they employ a maximum a posteriori method on the laptop. They use a 4-pole sampling method as opposed to a 2-pole method to reduce the effects of inconsistent skin contact impedance.

They characterize the accuracy of their tomography readings with their affordable COTS system by running it on a tube filled with saline solution and different shapes (Section "FIDELITY EXPERIMENTS").

The final system can differentiate between 2 hand gestures with an accuracy of ~95%. I would have liked to see a confusion matrix.

Hot takes:
personal interest: 6/10

paper quality / novelty: 7/10
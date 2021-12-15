## Energy-Efficient Image Compressive Transmission for Wireless Camera Networks
#### [[authors/Yong Wang]], [[Dianhong Wang]], [[Xufan Zhang]], [[Jun Chen]], and [[Yamin Li]], 2016

#### Summary
Wireless camera nodes capture an amount of data that's far too large to send raw over a wireless network. Widely-used video compression techniques weren't designed with this sort of application in mind. They're power-hungry (our nodes don't have much power), they're memory-hungry, and they're not robust to packet loss (wireless mesh networks may drop a lot of packets). The authors introduce a compressive-sensing based video compression scheme and use it to construct a wireless camera node.

The proposed compression scheme first uses an online background classifier to distinguish between ROI and non-ROI tiles (Section IV.A); non-ROI tiles are encoded less frequently and with less precision. Next, it takes a block-based Haar Wavelet Transform and compressively samples the Haar Coefficients, using the sparsity of the Haar transform to dictate the number of samples to take (Section IV.B). The compression quality is modulated depending on the amount of remaining power; as a node's battery drains, its image quality will get progressively worse (Section IV.C).

The authors construct a sensor node with an Application level ARM processor running Linux, Zigbee and WiFi radios, and a 1.3Mp grayscale camera. They show their system recording video at different packet loss rates.

#### Strengths
 * They identify a few key places where a naive wireless camera node works too hard.
 * They build and test on real hardware
 * They develop a working end-to-end system that uses their technique (Section VI & Figure 9)

#### Weaknesses
 * Transform into Haar Wavelet Domain and THEN into CS domain only *barely* makes sense. Some justifying discussion would be good to know that these folks know what they're doing. Yeah, I know that putting it into the Haar Domain on the edge sensor gives them some idea of how many samples they need to take. And I know that
 * Their heuristic for trading off between power consumption and image quality could have been much more sophisticated and taken into consideration radio power consumption (which I assume varies with link quality).
 * Hardware platform is very high power

#### Additional Comments
It seems like the use of compressive sensing here is just as a way to modulate compression quality and provide some robustness to packet loss. I think there could be other, possibly better ways to achieve these goals... Maybe fountain codes? The conversion to the compressive domain AFTER taking the Haar Transform seems unnecessary.

Also, their quip at the start of the paper that JPEG is too power intensive doesn't make much sense. The scheme they have put together is much more energy intensive than JPEG.

Section IV.C disappoints; they could have also modulated depending on the power consumption of the radio over time (I assume that a weak link will require more power to send, depending on how channel state the protocol keeps track of).

Keywords: [[wireless]] [[keywords/wireless-sensor-networks]] [[compressive-sensing]]
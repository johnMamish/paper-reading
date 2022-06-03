## An Energy Efficient JPEG Encoder with Neural Network Based Approximation and Near-Threshold Computing
#### Zhihui Wang, [[Shouyi Yin]], [[Fengbin Tu]], [[Leibo Liu]], Shaojun Wei, 2018
#### Summary
In order to perform JPEG compression, the computationally expensive 8x8 DCT operation is required, which takes power. For JPEG to work properly, the DCT doesnt need to be calculated exactly; some earlier work has investigated the use of approximate computing techniques to compute the DCT instead of regular arithmetic units.

The authors propose using a small, fully-connected neural network to calculate the DCT. Using a DNN has 2 major benefits: **more parallelism is exposed** and **power consumption and accuracy can be scaled**.  The authors use a fully-connected DNN with 3 - 5 layers and a total of 2 - 64 hidden neurons. The input and output layers are naturally fixed to size 64. The authors find that "the trained 64-16-64 neural network topology... has an acceptable... quality loss... \[and\] low energy consumption".

They synthesize their design and simulate the compression of 640x480 color images. They find that their design takes about 1/10th the power of \[7\].

Approximate computing is an excellent lever for achieving a smooth tradeoff of energy vs "information per bit" in compression schemes.

#### Strengths
  - The work exposes a knob for trading off between accuracy and power consumption (network depth / size)

#### Weaknesses
  - System uses an off-chip DRAM which immediately "prices them out" of the 10mW regime
  - New set of network weights needed to adjust the quality-vs-power knob
  - New set of network weights needed if you want to change the quantization table
  - FPS claimed in V.B doesn't line up with table II
  - Comparison of this work to Reynders doesn't seem apples-to-apples.
  - Power consumption at different network sizes not tested.

#### Additional comments
The paper has a pretty interesting idea; I can't help but feel like there are a lot of ways it could be improved. The use of a DNN here feels like hammering in a screw. 
 - Would've liked to see a comparison in the number of multiplies, adds, and divs saved by the DNN
 - Did they use floating point or 
 - Paper says about citations \[6,7\] "sub-threshold designs are not suitable for embedded devices due to intolerable perfoamnce penalties". No citation or further clarification is given?? Maybe they're talking about tolerance issues.
 - They give power consumption in pJ / pixel. My jfpjc compressor deployed on iCE40 gets 2,480 pJ / pixel, about 20x more energy / pixel than theirs.

#### What potential directions of future work remain (if any)?

#### Interesting Citations
Interestingly, this paper cites a lot of work from Dennis Sylvester and David Blaauw.
 - [[papers/IEEE/ISSCC/2009/An ultra-low-energy multi-standard JPEG co-processor in 65 nm CMOS with sub-near threshold supply voltage]]
 - [[Low-power digital signal processing using approximate adders]]

Keywords: [[keywords/power-consumption]] [[keywords/compression]] [[keywords/jpeg]] [[keywords/camera]] 
Tags:
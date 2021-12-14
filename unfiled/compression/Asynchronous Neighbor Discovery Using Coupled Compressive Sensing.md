## Asynchronous Neighbor Discovery Using Coupled Compressive Sensing
#### [[Vamsi K. Amalladinne]], [[Dongning Guo]], et al, 2019

#### Summary
As sensor networks aggressively scale, it will be important to have efficient schemes for receivers to know which nodes they can hear transmissions from. Typically, this process of "neighbor discovery" takes many long, non-colliding transmissions; more recent methods have arisen which allow for collisions, but still require all transmitters to align their messages. The authors introduce an approach which - if a receiver is given the sum of a bunch of messages all offset by different (discrete, symbol-aligned) amounts in time, it will be able to figure out which tx-ers sent the messages.

Each device has a specific ID associated with it. This ID is expressed as a message which consists of sub-blocks of complex symbols chosen from a predetermined set. The complex symbols are padded with 0's to account for differing message delays. At the receiver, the sampled symbols can be expressed as the sum of the symbols multiplied by channel fading coefficients. This reduces to a Compressive Sensing decoding problem. I think the intuition is that it uses symbol transmissions as an incoherent domain for sampling the complex fading coefficients.

The authors show that similar or better than state-of-the-art performance can be had for smaller transmitted message sizes. The improvements to me don't seem drastic though. Moreover, the scheme isn't truly asynchronous - it assumes that symbol boundaries are aligned AFAICT.

#### Strengths
 - non-obvious cross-discipline application

#### Weaknesses
 - Novelty is limited; straightforward application of a well-understood technique in one domain to problem in a different domain.
 - Bothered by what I read as a lie in the title. This paper isn't TRULY asynchronous, it assumes that - although messages might not be aligned - all symbols are aligned.

Keywords: #keywords/neighbor-discovery #keywords/random-access #keywords/compressive-sensing #keywords/forward-error-correction #keywords/asynchronous-schemes #keywords/wireless-communication
Tags:

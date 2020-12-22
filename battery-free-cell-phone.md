The authors present a system design of a battery-free cell phone which relies on RF harvested from a basestation for power and backscatter for communication.

Existing work that uses backscatter radios requires an ADC/DAC and microcontroller to digitally encode the data which can then be sent on the backscatter channel. This is too power intensive for a battery-free device. As an alternative, the authors directly connect the microphone and speakers to the antenna, bypassing the need for an ADC/DAC to transmit the data. Because the microphone and speakers will load the antenna and degrade the power harvest capability of the system, an onboard microcontroller operating in the ~100nW-1uW regime can duty-cycle these analog components; the analog components are more heavily duty-cycled when harvested power is low. Moreover, when a call is not in progress, these components will be gated so that more energy can be harvested. Calls are initiated by digital backscatter transmissions from the microcontroller.

In the conclusion, the paper discusses potential encyption and TDM/FDM schemes, but these seem to me to require very nontrivial extension of the work.

Hot takes:
personal interest: 7/10
paper quality / novelty: 7.5/10

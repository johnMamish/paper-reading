## BackDoor: Making Microphones Hear Inaudible Sounds
#### Nirupam Roy, Haitham Hassanieh, Romit Roy Choudhury, 2017
#### Summary
Microphones offer a channel for data communication, however, communicating via microphones can be challenging because - for most microphones - only a small band between 20kHz and 24kHz is available for transmission without bothering human hearing. BackDoor proposes a method where sounds much higher than the typical microphone cutoff frequency can produce artifacts recordable by microphones. These sounds are not audible to humans but are audible to microphones due to nonlinearity in the microphone diaphragm.  This can be used to broaden the microphone communication channel to the full 24kHz typical of microphones. It can also allow for covert jamming of audio recordings.

The math - described in section 3 - is pretty straightforward: BackDoor transmitters play 2 seperate frequencies far into the ultrasonic range. Because nonlinearities in the rx mic diaphragm can be modeled by an infinite power series, the ^2 term of this power series will cause frequency modulation through sinusoid multiplication, e.g. generating a 10kHz tone from a 50kHz and 40kHz tone. They also discuss different data modulation schemes, developing an interesting pre-emphasis scheme to avoid audible artifacts when using FM transmission (Section 4 "coping with the ringing effect").

They perform a number of validation studies. First, they compare percieved human loudness with microphone recorded loudness, comparing against how loud a pure tone and white noise is perceptually for similar recorded loudness levels (Table 1) as well as seeing how well audio is jammed by a loud BackDoor signal that's still inaudible (Section 5.4). They also look at how much data BackDoor can transmit compared to other inaudible techniques (Figure 17) and how well it performs with interference.

#### Strengths
  - Very clever method - inaudible noise is picked up by microphone
  - I liked their thorough treatment of AM and FM communication.

#### Weaknesses
  - Limited applicability / real world use
  - No discussion of whether or not this works on non-mems microphones.

#### Additional comments
(Further justify lists, if necessary, with the most critical items first)

#### What potential directions of future work remain (if any)?
I'd be interested in seeing how MEMS mics can mitigate this issue. Are there design techniques that can reduce the nonlinearity? If not, why?

I suspect that BackDoor is hard to eliminate for MEMS mics: all of their tested commercial products (Figure 6) exhibited this behavior.

Keywords:  [[keywords/audio]] 
Tags:
Read date: [[july]]
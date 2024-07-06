

# Circuit Techniques
## MFCs
* [[Impact of switching of the electrical harvesting interface on microbial fuel cell losses]]
* Loss analysis of flyback in discontinuous conduction mode for sub-mW harvesting systems
* 100 μW coreless flyback converter for microbial fuel cells energy harvesting
* Equivalent Electric Circuit Modeling and Performance Analysis of a PEM Fuel Cell Stack Using Impedance Spectroscopy

## Solar
- [[Power Controller Design for Maximum Power Tracking in Solar Installations]]
  Foundational, mostly focuses on a control law to choose buck regulator duty cycle u(t) to maximize input and output power.

## Coil-Based
* [[Electromagnetic Energy Harvester Interface Design for Wearable Applications]]
  *** This is the one you were really inspired by from the Tsinghua prof

## "Resistor Emulation"
- [[Resistor Emulation Approach to Low-Power RF Energy Harvesting]]
  Even though this paper is aimed at RF harvesting, in principle they are proposing the same thing that we want to do - have a DC/DC regulator behave like a resistor at its input port.
  They refer to this technique as **resistor emulation** and say that it has already found broad use in switching PFC circuits.
  
## Piezo-Based
* Classic Switching regulators
	* [[Adaptive Piezoelectric Energy Harvesting Circuit for Wireless Remote Power Supply]]:2002
	  Classic paper - adjusts switching regulator duty cycle to achieve max power.
	* [Optimized Piezoelectric Energy Harvesting Circuit Using Step-Down Converter in Discontinuous Conduction Mode](https://ieeexplore.ieee.org/abstract/document/1189621): 2003
	* [[Buck-Boost Converter for Sensorless Power Optimization of Piezoelectric Energy Harvester]]
* SSHI
	* [Semi-passive damping using continuous switching of a piezoelectric device](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/3672/0000/Semi-passive-damping-using-continuous-switching-of-a-piezoelectric-device/10.1117/12.349773.full): 1999
	  Introduces SSD - a precursor of SSHI - to achieve mechanical damping. Guyomar & Richard.
	* [High-performance piezoelectric vibration energy reclamation](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/5390/0000/High-performance-piezoelectric-vibration-energy-reclamation/10.1117/12.532709.full?SSO=1): 2004
	  [Toward Energy Harvesting Using Active Materials and Conversion Improvement by Nonlinear Processing](https://ieeexplore.ieee.org/abstract/document/1428041): 2004
	  [A comparison between several vibration-powered piezoelectric generators for standalone systems](https://www.sciencedirect.com/science/article/pii/S0924424705006151): 2005
	  Guyomar & Richard introduce SSHI
* SECE
	* [A 30nA Quiescent 80nW-to-14mW Power-Range Shock-Optimized SECE-Based Piezoelectric Harvesting Interface with 420% Harvested-Energy Improvement](https://ieeexplore.ieee.org/abstract/document/8310228): 2018, ISSCC
	  Brief ISSCC design paper
	* 

# Modelling and MPPT Techniques
## Microbial Fuel Cells
 * Deep learning
	 * [Q-Learning based Maximum Power Point Tracking Control for Microbial Fuel Cell](http://www.electrochemsci.org/papers/vol15/151009917.pdf) 

## Wind Energy
* Classical Modelling
* Deep learning
	* [[Reinforcement-Learning-Based Intelligent Maximum Power Point Tracking Control for Wind Energy Conversion Systems]]

## Photovoltaic
 * Deep learning
	 * [A Reinforcement Learning-Based Maximum Power Point Tracking Method for Photovoltaic Array](https://downloads.hindawi.com/journals/ijp/2015/496401.pdf): 2015
	 * [[Maximum Power Point Tracking of Photovoltaic System Based on Reinforcement Learning]], 2019

# Questions
- In [[Resistor Emulation Approach to Low-Power RF Energy Harvesting]], why do they turn on and off a square wave? why not just adjust the duty cycle of the pwm directly? Some thoughts on why this might be:
   1. Control circuitry to precisely adjust PWM would be too high power (I bet this is it.)
   2. Keeping a square wave improves resistor emulation (not sure about this one ?)
   3. Makes it easier to keep circuit in DCM (also not sure about this one)

# Extra stuff
- A Report on Semiconductor Foundry Access by US Academics
  Some resources about fabricating ASICs as an academic.
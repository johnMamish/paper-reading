pA current sensing mainly has applications in biology, nuclear detection, and high energy physics. These are the best places to look for existing work.

### High level view of circuit techniques:
#### Shunt-resistor based
This method is the one you're most familiar with. It works well for the > ~10pA range, but Johnson noise, burden voltage, and offset voltage (of the opamp) are issues at very low current range.

#### Trans-impedance amplifier (TIA)
There are 2 ways to implement a TIA: resistive and capacitive.

##### Resistive TIAs


##### Capacitive TIAs


##### "Charge balancing" / "recycling" integrator
This is a TIA set up with external circuitry such that it acts as a current-to-frequency converter. Once the voltage over the TIA exceeds a certain threshold (i.e. a fixed amount of current has been integrated), a pulse is emitted and an amount of charge corresponding to the TIA threshold is subtracted from the TIA's integration capacitor.

This method appeals to me because
 - It is very easy for me to understand how it works
 - ADC is handled by a very simple delta-sigma like scheme
 - Existing work has validated that it's possible to make this method work at very low currents with low power.

**However**, I don't have substantive justification as to why this type of current ADC would be better than a regular capacitive TIA just hooked right into a traditional ADC. 


[[Noise Analysis and Performance Comparison of Low Current Measurement Systems for Biomedical Applications]] is an excellent overview of different established circuit techniques.


 * [[Noise Analysis and Performance Comparison of Low Current Measurement Systems for Biomedical Applications]]
   TODO: investigate citations 5 – 13 from this publication
 * [[Sub-picoampere, 7-decade current to frequency converter for current sensing]]
 * [[Self-Powered Soil Moisture Monitoring Sensor Using a Picoampere Quiescent Current Wake-Up Circuit]]
 * [[Wide-Range, Picoampere-Sensitivity Multichannel VLSI Potentiostat for Neurotransmitter Sensing]]

##### Voulgaris / Kayal ("Utopia" ASIC)
These works were produced by grad student Evgenia Voulgari working under Maher Kayal at EPFL in Switzerland. They are all riffs on the same basic "charge balancing integrator" circuit.
 * [[Sub-picoampere, 7-decade current to frequency converter for current sensing]]
   Original "Utopia" ASIC paper
 * [[A front-end ASIC for ionising radiation monitoring with femto-amp capabilities]]
   Design presented is essentially idential to utopia paper (looks like same ASIC), but more design details are given.
 - [[Design of a fA wide dynamic range ADC for current sensing]]
   This is version 2 of the Utopia ASIC
 - [[Utopia: A Nine Decade Femtoampere Sensitivity Current Digitizer and Its Application in Ionizing Radiation Monitoring]]
 * [[Charge-balancing current integrator with large dynamic range]]
   Old paper (1983) that gets good results. Precursor to Voulgari, Kayal et. al "Utopia" work. Has some good theoretical backing for contextualizing these newer works.

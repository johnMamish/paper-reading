KaiYuan Yang is working with us on the DARPA project and specializes in low-power analog circuits. He could be a good collaborator for future work on energy harvesting front-ends.

## A2: Analog Malicious Hardware
#### Kaiyuan Yang, Matthew Hicks, Qing Dong, Todd Austin, Dennis Sylvester, 2016

#### Summary
Malicious hardware that creates security flaws allowing things like privilege escalation can be inserted into a processor's design at fabrication time, after place-and-route has been provided by a client. For instance, a malicious actor working act a semiconductor foundry could insert a circuit which will escalate privilege when a specific, highly improbable but completely legal sequence of user-space actions is carried out. An attacker working in cooperation with the foundry employee would know how to trigger this "sleeper cell" on processors fabricated with the malicious hardware. Typically the crafting of these attacks relies on a relatively large digital circuit. Because of their size, these malicious circuits can be detected with side-channel power analysis. Furthermore, the attacker might not be able to find a convenient place to inject the malicious circuit.

The authors demonstrate a mixed-signal circuit which only takes the space of a couple of logic gates, but which can trigger on an arbitrarily complicated sequence of events. They select wires from the design as inputs for their circuit, which transfers a known amount of charge onto the gate of a MOSFET each time the selected wires toggle from low to high via a capacitor charge-sharing mechanism (figure 4). The MOSFET being charged naturally leaks current, but if enough toggles occur in a sufficiently close window, it will reach a voltage where it can toggle a schmitt trigger, triggering the malicious behavior. The wires that transfer charge can be selected so that they toggle when exceedingly rare events occur.

The circuit takes 2 orders of magnitude less than similar digital-based attacks and only requires one metal layer. Because of the size and simplicity of the circuit, it's difficult to detect via side-channels (section IV.B.1.2) or by visual inspection. The authors fabricate a real processor which contains the described attack mechanism, showing that the attack can be carried out in real hardware. They also analyze the likelihood of benchmark programs accidentally tripping the malicious hardware and determine that it's exceedingly unlikely.

They discuss mitigation strategies that involve splitting the fabrication of the chip among 2 foundries using 3d-IC technology or by asking one foundry to dope the chip and another to metallize it.

#### Strengths
 * Malicious circuit is much smaller than similar existing attacks
 * Demonstration of technique in real hardware

#### Weaknesses
 * IDK

Hot takes:
personal interest: 5/10\
totally outside my area of interest in terms of application, but techniques are possibly relevant to low-power computing\
paper quality / novelty: 8/10\


## CAP-RAM: A Charge-Domain In-Memory Computing 6T-SRAM for Accurate and Precision-Programmable CNN Inference
#### Kaiyuan Yang, et. Al (2021)

#### Summary
Memory bottleneck.

The authors propose to speed up CNN inference by doing a lot of the computing in-memory. They achieve this via a

#### Armande Capitaine, Gael Pillonnet, Thibaut Chailloux, Adrien Morel, and Bruno Allard, 2017
#### Summary
Microbial fuel cells (MFCs) are energy sources which can generate electricity from biological processes found in nature; they represent an excellent, enviornmentally friendly energy harvesting opportunity for environmental monitoring systems. Impedance matching is important to harvest the most energy possible from MFCs, but until now only DC characteristics of MFCs have been considered. This analysis is insufficient; there are internal mechanisms in the MFC that can be modeled as capacitive that affect the efficiency of switching regulators.

The authors use electrochemical impedance spectroscopy (EIS) to characterize MFC impedance at different frequencies. They find that the MFC can be modeled as having a very large RC branch with a time constant of 10s of s (which they attribute to biological transport effects) and a smaller RC branch with a time constant of 100s of us (which they attribute to electrical double-layer effects). The authors connect the characterized MFC to a switching regulator from an earlier work and determine how much power is lost to each of these effects due to switching. The authors find that about 5% and 48% of biologically available power is lost to these 2 effects. The authors propose that these losses can be eliminated by increasing switching regulator frequency (which is undesirable due to increased switching loss) or simply by adding a capacitor across the MFC's terminals (which is trivial).

The findings of this work will be extremely useful in designing a practical MFC harvesting circuit. Not only do the authors characterize sources of losses in the MFC, they also provide some methods for preventing these losses. Their work gives a great starting point for further, more practical MFC switching development.

#### Strengths
* Straightforward analysis about things we need to know regarding MFCs
* Gives easy, practical solution to a real problem
* Switching regulator easy to build

#### Weaknesses
  - Lack of information about how MFC is prepared
  - Section 2 is basically a textbook intro about how EIS works; instead, they should've included more info about their specific experimental setup.

#### What potential directions of future work remain (if any)?
Build a switching regulator using these insights.

#### Citations
 * [[Equivalent Electric Circuit Modeling and Performance Analysis of a PEM Fuel Cell Stack Using Impedance Spectroscopy]]
   Highly-cited paper that lays some groundwork for proton exchange membrane (PEM) fuel cells. This paper works with a 1.2kW PEM.

Keywords: (link to pages under the keywords/ directory here)
Tags: (link to pages under the tags/ directory here)
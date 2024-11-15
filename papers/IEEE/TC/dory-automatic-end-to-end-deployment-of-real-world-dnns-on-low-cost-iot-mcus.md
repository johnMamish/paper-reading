## DORY: Automatic End-to-End Deployment of Real-World DNNs on Low-Cost IoT MCUs
#### Alessio Burrello , Angelo Garofalo, Nazareno Bruschi, Giuseppe Tagliavini , Davide Rossi , and Francesco Conti, 2021
#### Summary
Deploying DNNs to low-power edge systems is attractive, but challenging because energy constraints mean that these systems have a far different memory hierarchy than the conventional systems that most DNNs have been traditionally developed on. Namely, the "scratchpad memory" (on-chip SRAM) on a low-power microcontroller is manually managed and the relative cost of going to DRAM is higher than in other systems.

The authors develop a model describing the memory motion required for evaluating DNNs on a specific edge processor, the GAP8. They then pose the scheduling of loading DNN weights into on-chip SRAM as a **Constraint Programming** optimization problem. They develop a software package that takes in DNN descriptions and outputs C programs that orchestrate loading of DNN weights.

The authors compare their system to a tool supplied by the manufacturers of the GAP8 as well as to a tool that works on an STM32H7 that resides in a similar power class. They find that their method improves the performance of the GAP8 on inference tasks and far outperforms the STM32H7. They measure the raw GMAC/s performance on a single layer of MobileNet (Table 3) and a full end-to-end MobileNet with **128x128** and **192x192** images and a few different depth multipliers.

#### Strengths
  - Impressive experimental results
  - Very clear and in-depth description of method
  - Problem that they set out to solve seems like an obviously good problem to work on
  - VERY cool figures show energy vs FPS across different software configs.
#### Weaknesses
  - 
#### Additional comments
 * I should start doing projects with the GAP8 processor...
#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - Should read the PULP paper that describes a new architecture for edge DNN / vision processing

Keywords: (link to pages under the keywords/ directory here)
Tags: (link to pages under the tags/ directory here)
Read Date: [[november]] 2024
## Dominant-Current Deep Learning Scheme for EIT	
#### Wei, et. al, 2019
#### Summary
EIT is an ill-posed inverse problem where the 2-d or 3-d conductivity of a non-uniform material is to be determined by current and voltage readings taken from its perimeter. While this problem is really difficult, solving it effectively promises to give us portable, non-invasive, cheap, and effective medical imaging of the chest cavity. Existing methods for this inverse problem are very computationally expensive and are sensitive to noise.

Inspired by an iterative solver based on Bases-Expansion, the authors develop a deep learning model to deliver high quality EIT imaging. Their network takes as input low-quality EIT reconstructions; the network learns how to build higher quality reconstructions from lower quality ones. They train their network on random ellipse datasets built to approximate hart and lung phantoms. They test their system in a few different ways:
 - With numerically generated RED datasets
 - With data collected from a saline tank
As far as I can tell, they don't work with any data from a human body. Their reconstruction method yields shaper images and takes about ~15% of the time of their control method, BE-SOM.


#### Strengths
  - Their technique takes much less computational power
  - Their technique gives sharper images

#### Weaknesses
  - Testing and training mostly relies on numerical data
  - No testing on data from human bodies

#### Additional comments
Honestly, a lot of the math in this paper is inaccessible for a quick skim and went over my head. It would take a few hours of concentrated effort to understand what's going on here.

At any rate, I'm skeptical of their training methodologies. I (baselessly) suspect that their use of random ellipse datasets (REDs) with added noise won't be enough for real world applications. Yeah, they're learning a theoretically correct solution to a very hard inverse problem, but I don't know if it will work for the human body, with contact resistance and all the other shit that we have going on.

#### What potential directions of future work remain (if any)?
Speed up 3d EIT?

#### Citations

Keywords:  [[keywords/electrical-impedance-tomography]], [[deep-learning]]
Tags:
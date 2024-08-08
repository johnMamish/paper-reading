## Paper title
#### Bailey Miller, Hanyu Chen, Alice Lai, [[Ioannis Gkioulekas]], 2024
#### Summary
Recently, Neural Radiance Fields (NeRFs) have shown excellent performance in neurally modelling solids, however, NeRFs use a volumetric transport model for their underlying representation, even when modelling opaque objects. This is interesting because volumetric transport models are intended for modelling translucent objects. This work seeks to understand how NeRFs do this by developing a theory of modelling opaque objects with volumetric transport models.

Volumetric transport models work by representing translucent objects by a 3d probability density function (PDF): to render an object, rays are cast into the PDF, which represents the probability of a photon reflection. The authors give a definition of opaque objects (section 3.1) and then establish Theorem 4, which gives conditions for the exponentiality of the PDF of an opaque object.

Modeling opaque objects in this way leads to some properites of the volumetric PDF of an opaque object (that I don't fully understand TBH). They evalute the utility of their representation by building representations of physical objects with their representation and comparing the "Chamfer distance" (?) with the Chamfer distance of other representations.

#### Strengths
  - Theoretical underpinning that aims to explain a recent, very impressive result in deep learning (NeRFs)
  - Starts from first principles with a very simple definition of opacity and then derives mathematically interpretable results from that.

#### Weaknesses
  - I'd like it if they had a more extensive discussion section for non-experts
  - A clearer explanation of why just using a dirac-delta function doesn't work would be appreciated

#### Additional comments
This paper is definitely a little past my limit of understanding.

Keywords: [[deep-learning]], [[keywords/light-transport]]
Tags: 
Read date: [[july]]
## Depth from focus with your mobile phone
#### Suwajanakorn, Seitz, et. al, 2015
#### Summary
Image sensors with actuated adjustable-focus lenses have become ubiquitous; images produced by these systems can be converted into depth maps, but existing work on Depth from Defocus assumes stationary scenes and calibrated laboratory setups; these assumptions rule out the use of handheld cameras for generating depth images. In this work, the authors show that handheld commodity smartphone cameras can be used to generate depth images.

The authors develop a novel image processing pipeline to handle stacks of differently-focused images under motion. First, they apply affine transforms to handle rolling shutter effects and focus changes; next, they run optical flow on frames that are adjacent to each other in the stack, assuming that the stack is dense enough that adjacent frames have flow. Next, by assuming that depth values are locally constant, the authors are able to pose a tractable optimization problem that allows for the recovery of camera parameters, which allows the calculation of depth.

The authors capture data using a commodity smartphone without special software - they just make it autofocus. Each image stack consists of 20 - 30 differently focused images and takes ~40 minutes (!!) to process. Depth images are presented, which are heuristically compared to photographs without a rigorous error analysis. This work shows how 

#### Strengths
 - Impressive results
 - Data captured with commodity camera

#### Weaknesses
  - Experimental error analysis left something to be desired; why not have depth ground truth?
  - Images very low-resolution.

#### Additional comments
IMO this paper does an exemplary job of using previous work. They use existing focal flow software and existing optimization software. It seems like they've written very little software on their own.... this is how research ought to be done!

#### What potential directions of future work remain (if any)?

#### Citations
Some comments about the citations
 - An Obsidian-hyperlinked list of some interesting citations
 - If I want to read the paper later, I can create a new article in the "Need to Read" folder

Keywords: [[keywords/3d-imaging]]
Tags:
Read date: [[read date/2024/november]]
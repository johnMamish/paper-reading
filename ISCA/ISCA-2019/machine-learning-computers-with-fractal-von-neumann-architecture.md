Modern machine learning accelerators are typified by heterogenous cores, which can be error-prone and labor intensive to program. The authors propose a "fractal core" which consists of nested homogenous cores which are capable of executing similar types of operations. AFAICT, these cores will be suited to working out problems that are amenable to divide-and-conquer techniques (section 2.2).

I wasn't able to fully grok this paper in the limited time that I spent reading it, so the following opinion is unfair, but... I'm very skeptical. This feels like a slick solution that's looking for a problem. The authors lack solid justification (like a user study) that their architecture is easier to program because of its "fractal" structure; they just rely on sloc count for a set of test programs on GPUs to justify that their architecture is easier to program... which leaves a lot to be desired.

Hot takes:
personal interest: 3/10
paper quality / novelty: 6/10 (impressive engineering, questionable motivation)
I have almost no idea what's going on here, and the paper's abstract / intro didn't explain things all that well.

AFAICT, the issue is that different schedulers in data centers schedule with different metrics in mind (section 3.2.1. might have the best explaination; the intro doesn't explain that well). The authors of this paper propose a scheme / group of labels that can be passed from schedulers that are focused on temporal issues (latency, etc) up to schedulers that are focused on "spatial" issues (resource (core, memory, network, etc) usage). This allows the schedulers to jointly optimize. I'm not sure - once the labels are created - how the schedulers optimize with that new info.

Hot takes:
personal interest: 2/10
paper quality / novelty: 7?/10
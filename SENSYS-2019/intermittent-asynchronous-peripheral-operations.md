Having systems that are robust to repeated, unexpected power loss is critical to the development of battery-free energy harvesting systems. Most work so far to this end has focused on checkpointing program execution state. Having peripherals that asynchronously do work independently of the CPU core is a critical resource- and power- saving technique for embedded systems; existing checkpointing techniques only focus on saving execution state, peripheral state is an afterthought that's implemented ad-hoc.

The authors propose a general framework for saving peripheral state by representing all CPU interactions with peripherals by fixed API requests and by representing the peripheral's progress towards the CPU's requests with a state machine. This bounds the memory required to checkpoint the peripheral's operating state and gives enough info to reconstruct peripheral state provided that the API follows certain guidelines and that certain atomicity guarantees are met by the peripheral's API.

Hot takes:
personal interest: 8/10 (directly relevant to Josiah's research)
paper quality / novelty: 8/10 (seems great to me).
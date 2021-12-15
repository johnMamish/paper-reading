Hot takes:
personal interest: 6/10
paper quality/novelty: 6/10

Research opportunity: prefetching for power-aware architectures.

Cache prefetchers need to balance aggressiveness with accuracy. If a prefetcher is too aggressive, it will fetch all of the memory needed, but will evict lots of useful cache lines and take up a lot of bandwidth as it does this. If a prefetcher is too careful, it just won't do anything.

The authors propose an addition to prefetchers which can be added on to any prefetcher. They put a neural network right after the prefetcher that is trained on-line to block prefetches that it thinks won't help. This means that you can have a very aggressive prefetcher which makes tons of shitty guesses, and hopefully their network will filter things out.

The authors work with a state-of-the-art prefetcher (Signature Path Prefetcher (SPP)). SPP has a confidence tracker which tells how likely it is for an issued prefetch to be worthwhile. They take out this confidence tracker, replace it with their NN, and re-tune SPP to be more aggressive so that it can take advadvantage of the better confidence tracker. They use "ChampSim" for simulation.
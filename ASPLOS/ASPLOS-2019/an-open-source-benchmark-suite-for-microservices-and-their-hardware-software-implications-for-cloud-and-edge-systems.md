There are a number of compelling software engineering reasons that microservices have become ubiquitous in servers (Section 1, paragraphs 2 - 4). However, the workload of microservices is drastically different than monolithic services that large server clusters were individually developed for; microservice-based workloads have different networking requirements, change cache pressure, and even result in changes in microarchitectural profile (e.g. branch mispredicts) (Figure 10). The wide adoption of microservices is pushing architectural changes on a microarchitectural and system level.

The authors present a new benchmark suite for evaluating architectural changes for systems that support microservices. The benchmark suite comprises a social network, e-commerce service, media service, banking service, and drone swarm manager, each of which is composed of microservices. They use their benchmark to perform a brief evaluation of architectural effects of microservice use on existing architectures.

Hot takes:
personal interest: 3/10
The only thing I can get from this is a great example of a paper introducing a new benchmark... which can be important for emerging computation fields.

paper quality / novelty: 9/10
absolute unit
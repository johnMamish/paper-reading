As the number of IoT devices and device designers proliferates, it becomes harder to ensure security of new IoT devices. You should be able to trust a device before bringing it into your home because insecure devices can compromise your entire home network. The authors consider a microcontroller onto which it's impossible to load vulnerable code. This is socially useful because it provides a single point of trust; if the people making the microcontroller are trusted, then any program that can possibly loaded onto the microcontroller will also be trusted.

To this end, the authors propose a hardware static program analysis unit called "bouncer" which refuses to load program code in which it detects things like bad control flow, type misuse, etc. Static program analysis for typical ISAs and programming languages is still a somewhat open problem AFAIK; even partial solutions take over hundreds of thousands of lines of code. To get around this, the authors use a very nontraditional processor ISA called "Zarf" which is funtionally oriented and easy to analyse.

Surprisingly, with this restricted ISA, their static analysis unit is just a state machine that only takes ~0.01mm^2 when synthesized in 32nm technology. Fun!... they use yosys and smt to synthesize and verify their design!

Hot takes:
personal interest: 3/10
paper quality / novelty: 8/10
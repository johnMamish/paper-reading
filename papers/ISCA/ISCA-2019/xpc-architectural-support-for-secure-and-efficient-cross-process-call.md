Microkernels are experience a resurgence of interest because of their improved reliability, extensibility, and security; however, by nature ukernels have more tasks running that require more inter-process communication (IPC). Inefficiency in IPC makes microkernels less feasible.

The authors present architectural extentions that make IPC take significantly fewer cycles. They primarily focus on optimizing context switching and zero-copy IPC messages. Previous work has looked at zero-copy IPC messages, but according the authors, these previous works either result in a prohibitive number of TLB evictions or require significant change to kernels.

They claim that their extensions require little change to kernels and a very small amount of extra hardware.

They add their extensions to an FPGA softprocessor and modify 2 microkernels and a monolithic kernel (Android Binder) to test. They are able to speed up IPC by a factor of a lot.

Hot takes:
personal interest: 4/10
paper quality / novelty: 8/10
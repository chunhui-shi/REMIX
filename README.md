# REMIX: Online Detection and Repair of Cache Contention for the JVM
## Ariel Eizenberg, Shiliang Hu, Gilles Pokam , Joseph Devietti
### Published in PLDI 2016

As ever more computation shifts onto multicore architectures,
it is increasingly critical to find effective ways of dealing
with multithreaded performance bugs like true and false
sharing. Previous approaches to fixing false sharing in unmanaged
languages have employed highly-invasive runtime
program modifications. We observe that managed language
runtimes, with garbage collection and JIT code compilation,
present unique opportunities to repair such bugs directly,
mirroring the techniques used in manual repairs.
We present REMIX, a modified version of the Oracle
HotSpot JVM which can detect cache contention bugs
and repair false sharing at runtime. REMIX’s detection
mechanism leverages recent performance counter improvements
on Intel platforms, which allow for precise, unobtrusive
monitoring of cache contention at the hardware
level. REMIX can detect and repair known false sharing issues
in the LMAX Disruptor high-performance inter-thread
messaging library and the Spring Reactor event-processing
framework, automatically providing 1.5-2x speedups over
unoptimized code and matching the performance of handoptimization.
REMIX also finds a new false sharing bug
in SPECjvm2008, and uncovers a true sharing bug in the
HotSpot JVM that, when fixed, improves the performance
of three NAS Parallel Benchmarks by 7-25x. REMIX incurs
no statistically-significant performance overhead on other
benchmarks that do not exhibit cache contention, making
REMIX practical for always-on use.



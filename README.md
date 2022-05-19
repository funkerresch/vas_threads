# vas_threads
A (in principle) lock- and heap-free threading library for realtime (audio) applications

vas_threads is part of the VAS (Virtual Acoustic Spaces) DSP library. I put it in a separate 
repository as it might have other applications apart from using it in combination with my own DSP library:)
It uses pthreads and therefore cannot be completely lock-free as pthreads needs a lock for the conditional wait.
But by using an atomic, lock-free queue implementation for each individual thread this lock is never accessed by anything else.

vas_threads is based on two other repositories:

https://github.com/Pithikos/C-Thread-Pool/blob/master/thpool.h by Johan Hanssen Seferidis.

And

https://github.com/Taymindis/lfqueue by Taymindis Woon.

Because I had to modify some significant parts in both repositories (and therefore break compatibility) a could not
use them as submodules. I added two examples as Pure Data objects from the VAS library: A multithreaded non-equal-partition
convolution reverb and a binaural renderer which calculates early reflections in addition to the direct signal. 

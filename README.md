# vas_threads
A (in principle) lock-free thread library for realtime audio applications

vas_threads is part of the VAS (Virtual Acoustic Spaces) DSP library. I put it in a separate 
repository as it might have other applications apart from using it in combination with my own DSP library:)
It uses pthreads and therefore cannot be completely be lockfree as pthreads needs a lock for the conditional wait.
But by using an atomic, lock-free queue implementation for each thread this lock is never accessed by any other thread.

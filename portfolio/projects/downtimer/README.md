# Downtimer

Downtimer is an education-friendly wrapper around JavaScript's `setTimeout` feature. I wrote it as a part of my work as a tutor for [UNSW's COMP1531](https://handbook.unsw.edu.au/undergraduate/courses/current/comp1531) course in order to help students learn asynchronous programming whilst making common pitfalls easier to diagnose and debug.

In particular:

* Students would often struggle to handle unexpected errors in timeout code, with these errors bringing down their entire process. Downtimer includes advanced logging to help students find these errors without causing a full server crash.
* Students would find it challenging to integrate Node's timer IDs into their data structures due to it being a non-serializable data-type. Downtimer uses simple strings for timer IDs, meaning students don't need to concern themselves with this complexity.
* Students with especially challenging concurrency bugs would be overwhelmed by the complexity of debugging. Downtimer has configurable logging to help students debug their work.
* Students aren't expected to continue using Downtimer in the real world, and so its API is very similar to real-world JavaScript timers.
**Dynamic memory allocation**

**Disadvantages of malloc**
* Application becomes nondeterministic
* Wasted RAM because of heap overhead
* Lost processor cycles binary searching available memory in heap
* Fragmentation in the heap, particularly if mix buffer sizes

**Alternatives**
* Ping-pong buffer
* Circular buffer
* RAM overlays two different systems can share the same RAM - although they cannot use it at the same time
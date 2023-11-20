**Threads**

Process = an instance of a program that is operating in the OS with separate memory space
Threads = each process can contain multiple independent, lightweight concurrency units called threads although they share the same memory address space
Actors = higher level of abstraction, encapsulated state with message passing, non-blocking operations
Future = a parcel of work, runs on a thread but don't know which. Futures are 1. composable 2. work with callback methods 3. has a return type 4. no guarantee when a thread will be called
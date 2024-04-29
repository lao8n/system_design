**Heap**

**Definition**
* Also known as free store in C++ is where dynamic storage lives. It is shared among multiple threds in a program and needs to be explicitly freed by the programmer. This is where dynamic memory allocation occurs.

**Commands**
* `malloc`: From C stands for memory allocation (`calloc` is cleared memory allocation where all bits set to 0). Malloc involves casting the void pointer so don't have any time safety
* `new`: From C++. Object orientation requires calling a constructor for member initialization, and the destructor for object deletion. We can overload new and delete for proprietary behaviour quite easily. Placement new is a variation where pass preallocated memory and construct the object there. Shouldn't use new or delete in application code - only underlying abstractions
* `free`: From C
* `delete`: From C++
* handles: Does the new and delete for you.

**Problems**
* Memory fragmentation

![image info](./../../../../images/memory.png)

**Stack**

**Definition**
* Contiguous memory block with a fixed memory size, if a program exceeds this size it will crash. It stores automatically allocated variables such as local variables or function parameters. Each thread has its own stack memory. Allocation and deallocation is handled by the compiler. 
* This is where automatic memory allocation occurs.
* Faster than heap because simpler memory model

**Tips**
* Avoid recursion as stack exhaustion is easy to hit
* Try to get variables out of stack into registers
* Allocated at compile time, does not work if don't know how large it will be.

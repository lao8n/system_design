Problems with physical memory = 1. holes in address space 2. programs writing over each other

Virtual memory = mapping function from virtual to physical memory can guarantee that programs don't overlap. Even if not enough RAM to fulfill all possible memory addresses that is fine as can use slower harddrive for those. I.e. RAM acts as a cache for virtual memory. It guarantees us a fixed size address space which is largely independent of system configuration and OS guarantees that the virtual address spaces of different programs do not interfere.

Memory page = number of directly successive memory locations in virtual memory. Computer memory is divided into memory pages of equal size to make easier management by the Memory Management Unit

Memory frame = physical location in main memory
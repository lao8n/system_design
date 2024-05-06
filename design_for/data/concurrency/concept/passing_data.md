**Passing data**

1. We can pass data from the parent thread to a worker thread at startup e.g. in C++ using variadic templates or with lambda functions and variable capture
2. Can also pass information from child to parent using single use channels where the sending is called the promise and the receiving is called the future.
**Macros**

**Advantages**
* Code re-use without the overhead of function calls as the preprocessor replaces each macro with its definition. Particularly useful for small and frequently called functions
* Macros don't do type-checking which means the same macro can be used for integers, unsigned integers, floats etc. 

**Disadvantages**
* Macros don't do type-checking which makes it more dangerous
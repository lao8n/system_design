**ACID**

Stands for
* Atomicity = a transaction is a single unit of work - no partial transactions
* Consistency = database goes from one valid state to another
* Isolation = concurrent transactions do not interfere with each other - if two executed concurrently the final state of the database should be as if they were executed serially
* Durability  = once a transaction is committed it will remain committed even in the face of system failures 

Contrast to
* BASE = Basically available, soft state (system will change even without input because of eventual consistency mechanisms) and eventually consistent which is often favoured in NoSQL database
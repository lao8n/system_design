**Deadlock**

Deadlock = a program is one in which all concurrent processes are waiting on one another.

Coffman conditions for deadlock
* Mutual exclusion - concurrent process holds exclusive rights to any resource at any one time
* Wait for Condition - a concurrent process must simultaneously hold a resource and be waiting for an additional resource
* No Preemption - a resource held by a concurrent process can only be released by that process so it fulfills this condition
* Circular wait - a concurrent process P1 must be waiting on a chain of other concurrent processes P2 which are in turn waiting on it P1

Starvation = any situation where a concurrent process cannot get all the resources it needs to perform work. 

Livelock = programs are actively performing concurrent operations but these operations do nothing to move to the state of the program forward. Livelock is a specific case of starvation where no work is done, starvation is the more general case of at least some work is not done

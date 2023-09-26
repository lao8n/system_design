**Redis**

**Definition** key-value store where most of the data is cached useful for high throughput and low-latency applications. 

**How it works**
* Snap shotting and append-only files can be used to persist data.
* Single-threaded event loop using non-blocking IO operations and avoiding concurrency problems.
* Communicate with Redis using TCP or RESP protocol
* It uses LRU to evict old data.
* Redis cluster can be used to partition data across multiple nodes
* CP (CAP) if network partition. Replication is in memory, have tunable consistency.
* Redis sorted sets are atomic and have unique values in order

**Architecture**
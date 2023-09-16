**Cassandra**

**Definition**


**Key properties**
* Columnar store
* CA (availability-partition tolerance) system.

**How it works**
* Write path: 1. write update to commit log on disk 2. push to memory cache 3. when memory cache is full flush to SSTable on disk
* Read path: 1. check memory cache if available return 2. if not available use bloom filter to identify which SSTable to search 3. Return the value from SSTable

**Used by**
* Discord
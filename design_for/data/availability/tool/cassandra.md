**Cassandra**

**Definition**: Open-source database, which is self-hosted, and manual management. 


**Key properties**
* Columnar store (2-d key-value store)
* AP (availability-partition tolerance) system 
* Eventually consistent although can be configured for strong consistency (can support quorum read to mimic own write but adds latency)
* Support CQL (like SQL)
* Write throughput is high
* Although it support blob storage of up to 2GB in practice only 1MB. Also doesn't work with row cache as attachments take up too much memory space

**How it works**
* Write path: 1. write update to commit log on disk 2. push to memory cache 3. when memory cache is full flush to SSTable on disk
* Read path: 1. check memory cache if available return 2. if not available use bloom filter to identify which SSTable to search 3. Return the value from SSTable

**Used by**
* Discord
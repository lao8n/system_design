**Log-structured merge tree**

Build a search index is very write heavy. The write-path is optimized by performing only sequential writes 

How it works
* New email arrives it is added to level 0 in-memory cache and then when data size reaches predefined threshold data is merged to the next level (on disk)

Used by
* Bigtable
* Cassandra
* RocksDB
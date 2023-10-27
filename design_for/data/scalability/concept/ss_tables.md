**SSTables** = sorted string table

Properties
* Immutable
* Sorted
* Compaction - overlapping keys get merged and rewritten into a single, larger SSTable
* Indexing = to enable fast loopkups indices can be embedded in the SSTable itself
* Write amplification = the data can end up being written multiple times - because of compaction for example
* Bloom filters = can quickly tell if a key is definitely not in an SSTable (although htere might be false positives) to make reads more efficient.

Used in
* Log-structured Merge Trees (LSM) like Cassandra, RocksDB and LEvel DB involves in-memory memtables and flushing to on-disk tables (SSTables)

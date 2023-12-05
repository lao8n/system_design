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

Bloom filters = is an array of m bits all set to 0 and uses k different hash functions. To add an element an element is passed through all k hash functions where the bits at these k indices are all set to 1. To check if an element is in the set the element is passed through the same k hash functions. If all the bits at the k indices are 1 the bloom filter reports it is possibly in the set. 
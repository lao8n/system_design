**Sharding**

**How it works**: rather than replicated data across databases, have different data stored in different places. Partitioning is like sharding but within a single table.

Options:
* Sharding strategy: sharding key could be random, `user_id` based or geographic, would like it to be even but this is difficult
* Celebrity problem: hot shards like celebrities on a social app may need a separate shard
* Resharding: at some point may need to reshard data to keep it even. Consistent hashing is needed for this to prevent unnecessary movement of data.
* Denormalize data: reduce the need for joins by combining tables
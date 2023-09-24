**Kafka**

**Definition** An event-streaming platform (distributed message queue).

**Key properties**
* Pub-sub model with producers and consumers 
* Topics allow repeated consumption, data is partitioned and processed by brokers and consumer groups
* Consumers groups keep track of offsets with one consumer per partition.
* Replication has leader do both writes and reads but in-sync replicas can have different levels of consistency based upon when offsets are commited where at-most-once (0 acknowledgements), at-least-once or exactly-once
* Disk reads are fast because sequential not random access. Use write-ahead logs.

**Architecture**

**Used by**
* 
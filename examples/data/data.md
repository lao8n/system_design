**Ways to improve data**

Horizontal scaling: +Availability
* Data Replication: +Availability +Scalability -Consistency
    * Single-leader replication +Consistency
    * Multi-leader replication +Scalability +Availability -Consistency
    * Leaderless replication +Scalability +Availability -Consistency

* Data Partitioning: +Scalability -Consistency
    * Shard data

* Data Latency: +LowLatency
    * Cache +LowLatency -Consistency

* Relational DB: +Consistency
    * Referential integrity of relational DB
* NoSQL DB: +LowLatency +Scalability
    * KV stores
    * Document stores
    * Columnar stores
    * Graph stores
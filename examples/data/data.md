**Ways to improve data**

Horizontal scaling: +Availability
* Data Replication: +Availability +Scalability -Consistency
* Data Partitioning: +Scalability -Consistency

System tools:
* Cache: +LowLatency -Consistency
* Relational DB: +Consistency
    * Referential integrity of relational DB
* NoSQL DB: +LowLatency +Scalability
    * KV stores
    * Document stores
    * Columnar stores
    * Graph stores
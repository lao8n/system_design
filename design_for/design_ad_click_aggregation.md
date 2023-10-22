**Design Ad Click Event Aggregation**:

**Step 1: Understand the problem and establish design scope**

Features
* Format of input file? Log files in different servers with `ad_id`, `click_timestamp`, `user_id`, `ip` and `country`
* Edge cases? Events arrive later than expected, duplicated events or system recovery.

Flows
* Queries? 
1. Ad clicks in last M minutes. 
2. Top 100 most clicked ads in the past minute with configurable parameters. 
3. Data filter by `ip`, `user_id` or `country` for the above two queries

Estimates
* Volume? Ad clicks per day and 2m ads in total. 30% Y-O-Y growth
* Ad click QPS: 1bn DAU x 1 ad / 100k s in a day = 10k
* Assume peak QPS is 5x so 50k QPS
* Storage 0.1KB so daily storage is 0.1KB x 1bn = 100GB

System design
* Latency? few minutes end-to-end

**Step 2: Propose high-level design and get buy-in**

2 APIs needed
* `GET /v1/ads/{:ad_id}/aggregated_count` with `from`, `to` and `filter` parameters. The response is `ad_id` and `count`
* `GET /v1/ads/popular_ads` with `count`, `window` and `filter` parameters. The response is `ad_ids`

Store both raw data and aggregated data
* Raw data = write heavy with limited reads (just backup) eith NoSQL like Cassandra or InfluxDB for write and time-range queries. Or could use columnar data formats like ORC, Parquet or AVRO
* Aggregated data = read heavy (auto-refreshing visualisation) - can use same database as before.

**Step 3: Design Deep Dive**

![image info](./../../../images/rate_limiter.png)

Compute
* Computation = trade-off between using event time (handling delayed events) and processing time (large lags). Typical solution is to add a watermark i.e. a rolling window and wait an extra 15s for events to be processed adding latency but improving accuracy. 2 types of windows 1. tumbling (fixed) window 2. sliding window (last 1 minute)
* Reliability = add queue in front of databases for raw and aggregated data. Reqruired for end-to-end exactly once semantics. Can recalculate data from raw data. Can scala Kafka with more partitions and more brokers. 
* Throughput: Use Kappa architecture to support both batch and streaming architectures. Can scale with more nodes i.e. multi-processing.

Data
* Scalability: NoSQL database scaled with hash ring of virtual nodes. 
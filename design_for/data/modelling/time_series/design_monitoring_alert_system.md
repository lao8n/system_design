**Design a**:

**Step 1: Understand the problem and establish design scope**

Features
* Internal or SAS? Internal
* Metrics? Operational system metrics e.g. CPU load, memory usage, disk space consumption and high level concepts like requests per second and running server count of a web pool. No business metrics
* Reduced resolution? Yes. After 7 days to 1 minute, after 30 days to 1 hour.
* Supported alert channels? Email, phone, pager duty and webhooks
* Logs? No
* Tracing? No

Flows
* Data collection and storage
* Alerting
* Visualization

Estimates
* Scale? 100m DAU, 1000 server pools, 100 machines per pool
* How long keep data? 1 year
* Num metrics? 1000 server pools x 100 machines per pool x 100 metrics per machine = 10m metrics

Distributed Systems
* Low-latency: for dashboards and alerts
* Scalability: to accomodate growing metrics and alerts. 
* Read/write: Heavy constant write load, spiky read load

**Step 2: Propose high-level design and get buy-in**

Flows
* Metrics collection -> push to time series data
* Alerting system -> sends queries to query service and then pushes to channels
* Visualisation system -> sends queries to query service

Choices
* Type of database: Use off-the-shelf time series database which is optimised for storage and provides functions for data.
* Push vs pull metrics: If pull need to use service discovery to keep track of servers, but because of scale need to a pool of metrics collectors and might get duplicates - can prevent with range on hash ring. Push metrics can reduce volume by aggregating and perhaps can have retry - to make sure doesn't fall behind needs to autoscale. Prometheus is pull, Amazon CloudWatch is push.
* Build vs buy: Worth buying alert system and visualisation system.

**Step 3: Design Deep Dive**

![image info](./../../../images/rate_limiter.png)

Compute
* Computation: where should aggregation happen in collection agent, ingestion pipeline or query side
* Reliability: there is a risk that if time series database is down the data is lost, can mitigate with a Kafka queue

Data
* Availability: it is okay if some data is dropped. Use NoSQL database for alert store to track progress (need at least once), use Kafka to help push
* Low-latency: could add a cache for the query service
* Modelling: Use time series database, might want to abstract behind a query service. SQL is hard to calculate time series functions. Optimisations in time-series db include data encoding and compression using deltas rather than values and downsampling

**Design a unique id generator**:

**Step 1: Understand the problem and establish design scope**

Requirements
* Doesn't have to be increments by 1 just correlated with time
* Just numbers
* Should be 10,000 per second

**Step 2: Propose high-level design and get buy-in**

Options
* Multi-master replication: auto-increment but increment by `k` although does not correlate with time and to avoid collisions need to use prime numbers. Doesn't work well with adding/removing servers
* UUID: unique ids that have very low probability of collisions however no association with time, and could be non-numeric and too large
* Ticket server: centralized auto-increment, but downside is single point of failure
* Twitter snowflake approach: generate id with: 1. timestamp 2. datacentre id 3. machine id 4. sequence number

**Step 3: Design Deep Dive**

Twitter snowflake approach
* Timestamp does most of the heavy lifting

**Step 4: Wrap Up**
* Clock synchronization: Network time protocol is one solution
* Section length tuning: More timestamp bits and less sequence bits is better for long-term, low currency applications
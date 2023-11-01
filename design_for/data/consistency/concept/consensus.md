**Consensus**

Approaches
* Paxos = works through a series of proposals each with a unique number, where nodes accept the proposal with the highest number. The problem is the algorithm can be difficult to understand and it doesn't guarantee liveness.
* Raft = divides time into terms where for each term there is a leader responsible for log replication. If a leader fails a new one is elected where the system ensures there is enough replication before commiting a lot entry to ensure data isn't lost
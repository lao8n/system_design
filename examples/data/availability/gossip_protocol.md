**Gossip protocol**

**How it works**
* Each node retains a membership list which contains member IDs and heartbeat counters.
* Each node periodically increments its heartbeat counter
* Each node periodically sends heartbeats to a set of random nodes which in turn propagate to another set of nodes
* Once nodes receive heartbeats, membership list is updated to the latest info
* If the heartbeat has not increased after a set period of time the member is considered offline

**Handling failures**
* Handle based on consistency model e.g. sloppy quorum
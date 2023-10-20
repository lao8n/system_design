**Redis Pub/sub**

**Definition** 

**Key properties**
* Each server handle roughly 100k subscriber pushes per second
* Messages are not persisted in memory or on disk - they are sent to subscribers of the channel and deleted i.e. stateless messages
* Subscriber list is maintained - therefore need to be careful of scaling.

**Architecture**

**Used by**
* 

**Alternatives**
* Use Erlang
**Consistency models**

Definitions
* Strong consistency = any read operation returns up-to-date write data. 
* Weak consistency = subsequent read operations may not see up to date
* Eventual consistency = specific form of weak consistency where given enough time all replicas will be consistent

Quorum consensus
* Strong consistency `W+R>N`
    * Fast read `R=1` & `W=N`
    * Fast write `W=1` & `R=N`
* Weak consistency `W+R<=N`
* Sloppy quorum of writes = don't enforce the quorum requirement of a specific set of nodes, the system chooses the first `W` healthy servers for writes and first `R` healthy servers for reads on the hash ring.
* Hinted handoff for downed DB = when a temporariliy down server gets changes back to achieve data consistency after another server temporarily takes over

Conflicts
* Versioning for weak writes using `(server, version)` pairs with vector clocks to choose latest

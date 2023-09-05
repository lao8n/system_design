**Multi-leader**

How it works:

What happens if it fails?
* Permanent failure: compare every piece of data with Merkle tree of hashes and copy if different

How is inconsistency resolved? By Quorum consensus
* Conflicts = Versioning for weak writes using `(server, version)` pairs with vector clocks to choose latest
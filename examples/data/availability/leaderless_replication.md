**Leaderless**

How it works: 

What happens if it fails?
* Permanent failure: compare every piece of data with Merkle tree of hashes and copy if different

How is inconsistency resolved? By Quorum consensus
    * Strong consistency `W+R>N`
        * Fast read `R=1` & `W=N`
        * Fast write `W=1` & `R=N`
    * Weak consistency `W+R<=N`
    * Sloppy quorum of writes if temporary failure, hinted handoff for downed DB
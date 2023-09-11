**Merkle tree**

**Summary**
* Problem: handling permanent failure
* Solution: anti-entropy protocol to keep replicas in sync where each piece of data is compared and updates to the newest version. Merkle trees is used for inconsistency detection and minimizing the amount of data transferred. 

**How it works**
* Hash tree = calculate bottom up hash trees for both versions
* Recursion = recurse down DFS whenever there is a difference in hash values
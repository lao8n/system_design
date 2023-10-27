**Cache**: enables low-latency data access.

**How it works**: temporary storage area that stores the result of expensive responses or frequently accessed data in memory so that subsequent requests are served more quickly.

What happens if it fails?
* It is a single point of failure, could have multiple caches
* Consistency is difficult as cache and database is not a single transaction - typically want either 2-phase commit or compensating transaction. Scaling across multiple regions is even more difficult

Caching strategies
* Cache-aside (lazy loading) = application code is responsible for loading into cache, invalidating stale entries and retrieving data etc. 
* Read-through = cache is responsible for loading data from the primary data store. When a cache miss occurs the cache itself fetches the missing data, stores it, and then returns it to the requester
* Write-through = every write operation to the cache is immediately mirrored to the primary data store this can provide strong consistency between cache and database but write operations have higher latency
* Write-back = write operations are directed to cache with periodic write behinds to the database (there is a risk of data loss before database write however)

Best suited
* Best suited for data that is read a lot but with limited modifications

Options:
* Caching strategy: read-through where if can access data in cache returns, otherwise queries database and stores in cache.
* Expiration policy: too stale vs too much reloading from database
* Eviction policy: LRU, LFU, FIFO
* External caches such as content delivery networks CDNs for static assets although cost, cache expiry and CDN fallback considerations

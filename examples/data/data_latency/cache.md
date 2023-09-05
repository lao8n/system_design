**Cache**: enables low-latency data access.

**How it works**: temporary storage area that stores the result of expensive responses or frequently accessed data in memory so that subsequent requests are served more quickly.

What happens if it fails?
* It is a single point of failure, could have multiple caches
* Consistency is difficult as cache and database is not a single transaction. Scaling across multiple regions is even more difficult

Best suited
* Best suited for data that is read a lot but with limited modifications

Options:
* Caching strategy: read-through where if can access data in cache returns, otherwise queries database and stores in cache.
* Expiration policy: too stale vs too much reloading from database
* Eviction policy: LRU, LFU, FIFO
* External caches such as content delivery networks CDNs for static assets although cost, cache expiry and CDN fallback considerations

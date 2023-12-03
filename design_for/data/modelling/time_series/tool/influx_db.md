***InfluxDB***

Time series database

Implementation = Time-Structured Merge Tree (TSM). TSM files are highly compressed, it keeps an in memory index to keep of what data exists and where it is located on disk.

It uses sharding, and write-ahead logs (before commiting to TSM files)

Merge tree = used in Log-Structured merge trees - written to memory store and then flushed to disk at multiple levels
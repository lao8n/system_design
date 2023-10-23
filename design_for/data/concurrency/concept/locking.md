**Locking**: 

**How it works**: 

Pessimistic locking = places lock on record as soon as a user starts to update it. Problem is can cause deadlocks and not recommended.

Optimistic locking = either implemented with version numbers or timestamps (better to use version as server timestamps can be inaccurate over time) where can only make update if version is larger that current version. Basically forces conflicts to fail but end up having one succeed and all others try and over and over again. Advantage is that no lock on database.

Database constraints = do optimistic locking on the database.
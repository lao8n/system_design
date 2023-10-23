**Saga**

**How it works** Saga is a sequence of local transactions. Each transaction publishes a message to trigger the next transaction step. If a step fails, the sage executes compensating transactions to undo the changes that were made in previous transactions. Saga, unlike 2PC which uses a single transaction, consists of multiple steps and relies on eventual consistency.
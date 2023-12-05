**SQS**

**Definition** Fully managed queuing service with automatic scaling.

**Key properties**
* At-least once: exactly-once can be achieved with deduplication logic in application layer.
* Data retention for 1 min-14 days
* Short and long polling for messages (unlike push-based for RabbitMQ and pull-based for Kafka)
* FIFO exact ordering of messages but lower throughput of 300 messages per/second compared to standard queue. Message groups can allow some scaling where messages are processed in different streams with ordering preserved within a message group
* When a message is received by a consumer it is not immediately removed but instead made invisibility per a visibility timeout as it waits for the deletion message from the processor. Then we use explicit delete to actually remove it

**Architecture**

**Used by**
* 
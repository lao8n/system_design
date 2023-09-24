**SQS**

**Definition** Fully managed queuing service with automatic scaling.

**Key properties**
* At-least once: exactly-once can be achieved with deduplication logic in application layer.
* Data retention for 1 min-14 days
* Short and long polling for messages (unlike push-based for RabbitMQ and pull-based for Kafka)
* FIFO exact ordering of messages but lower throughput of 300 messages per/second. Message groups can allow some scaling where messages are processed in different streams with ordering preserved within a message group

**Architecture**

**Used by**
* 
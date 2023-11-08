Exactly-once mechanics

* What is upstream fails
* What if Kafka fails
* What is downstream fails -> don't know 
* How prevent duplicates -> comp request ids generated on the requester side
* SQS FIFO queue - visibility timeout, message retention seconds, redrive policy for rpas , use dead letter queue
* DynamoDB cache - didn't use
* add monitoring etc.
* strongly consistent dynamod reads
* kafka setup -> when commit
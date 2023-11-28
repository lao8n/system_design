***RabbitMQ***

Definition = open source message broker that implements the Advanced Message Queuing Protocol. 

Overview
* Built in Erlang where lightweight processes allow a large number of concurrent connections efficiently
* Broker model = intermediary which accepts, stores and forwards mesages. Producers send messages to exchanges and consumers retrieve messages from queues
* Types of exchanges Direct, fanout, topic and headers. Messages are stored in queues until they are consumed. 
* Message acknowledgement = ensures no messages as consumers send acknowledgement back to RabbitMQ. 
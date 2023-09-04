**Ways to improve compute**

Vertical scaling: -Availability
* More CPU & RAM

Horizontal scaling: +Availability +Scalability
* Load balancer +Availability +Scalability
    * Stateless architecture enables autoscaling (if stateful would need sticky sessions) +Scalability
    * Failure detection by gossip protocol +Reliability

Interactions between systems: + Availability
* Queue
    * Decouples compute from data: +Availability
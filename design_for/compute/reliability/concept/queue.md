**Queue**: in memory component that support asynchronous communication

**How it works**: Producers publish to the queue and consumers consume and subscribe from the queue. This decouples components and allows one to continue even if another has failed. It also allows independent scaling of producers and consumers

**Types**
* Two types of queue
    * Point-to-point = each message consumed by one consumer with a poll operation
    * Event streaming = multiple consumers per topic

What happens if it fails?
* 

Best suited
* Compute logic is complicated and where it is useful to decouple parts of this logic either to 1. scale separately or 2. failure resilience
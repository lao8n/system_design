**Circuit breaker**: a design pattern that involves managing the interaction with a remote service or resource by monitoring failures and temporarily disabling the service when it behaves unexpectedly.

**How it works**: 
* Closed state = circuit breaker proxies request to the service or resource until the monitored failures breach a threshold and the breaker trips into an open state
* Open state = circuit breaker stops all attempts to call the service for a predetermined cooldown period> 
* Half-open state = Before closing the circuit breaker might transition to a half-open state where some requests are allowed through to check if the service is working again.

Advantages
* Prevents cascading failures where one service failing isolates it from the others. 
* It does still fail but it fails fast, and gives recovery time to the downed service
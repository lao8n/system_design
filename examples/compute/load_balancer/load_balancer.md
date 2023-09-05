**Load Balancer**: Enables horizontal scaling of compute +Scalability +Availability

**How it works**: public IP of load balancer exposed and it routes to private IPs of web servers

Options
* Stateful architecture: problem is every request needs to be routed to the same server. It can be done via sticky sessions but makes adding or removing servers difficult.
* Stateless architecture: compute retains no information about the user state. Typically session information can be stored in a more accessible NoSQL database.
* Geo-routing: Rather than all servers in one place, the load balancer can geo-route to specific data centres.
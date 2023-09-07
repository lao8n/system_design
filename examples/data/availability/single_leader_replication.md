**Single leader**

How it works: All writes go through single master, which is replicated to slave read nodes

What happens if it fails?
* If slave goes down, they are routed to other slaves, or failing that master
* If master goes down then slave is promoted, although there this is complicated if slave not up to date.
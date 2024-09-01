<b>Active-Active</b>
Load Balancer: Distributes client requests between Server 1 and Server 2.
Server 1 and Server 2: Both servers are active, handling requests and replicating data to the shared database.
Failover Mechanism: If one server fails, the other server continues to handle all requests, ensuring high availability.

<b>Active-Passive</b>
Load Balancer: Distributes client requests, primarily routing them to Server 1 (Active).
Server 1 (Active): The main server handles requests and interacts with the shared database.
Server 2 (Passive): The standby server, ready to take over if Server 1 fails.
Failover Mechanism: If Server 1 fails, Server 2 becomes active, ensuring continued service.

![alt text](https://github.com/pachouri/Architecture-and-System-Design/blob/main/diagram/Active_Active.gif?raw=true)

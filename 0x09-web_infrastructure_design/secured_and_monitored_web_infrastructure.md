# Web infrastructure design

## 2. Secured and monitored web infrastructure

### Specifics About This Infrastructure

- **What firewalls are for.** <br />
They monitor and filter incoming and outgoing network traffic based on an organization's previously established security policies.

- **Why is the traffic served over HTTPS** <br />
HTTPS is a more advanced and secure version of the HTTP protocol. It includes SSL, which is a part of the HTTPS protocol that performs encryption of the data.
SSL certificate - authenticates the website’s identity and establishes a secured channel for communication between the website and the client.

- **What monitoring is used for.** <br />
Tracking the health, metrics, and performance of your web servers, so you can ensure high-level functioning.

- **How the monitoring tool is collecting data.** <br />
Web servers are monitored for user load, security and speed.
Application servers are monitored for server availability and responsiveness.
Storage servers are monitored for availability, capacity, delay and data loss.

### Issues with this infrastructure

- **Terminating SSL at the load balancer level is an issue.** <br />
The traffic between the load-balancer and the server is unencrypted and, therefore, is vulnerable to data theft, session hijacking, and man-in-the-middle (MitM) attacks

- **Having only one MySQL server capable of accepting writes is an issue.** <br />
Some transactions committed on the master may not be available on the slave if the master fails.
- **Having servers with all the same components (database, web server and application server) might be a problem.** <br />
Your web site and database will share the same server resources (disk usage, memory, CPU). As a result, your database and web site will run slower than they would if they did not share resources with each other.

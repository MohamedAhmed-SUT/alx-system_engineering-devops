# 3-scale_up

### Project Overview

This project demonstrates a scaled-up web infrastructure where components are distributed across multiple servers for better reliability, scalability, and performance.

---

### Infrastructure Components:

- **3 Servers**:
  - One server for the **Load Balancer (HAProxy)**
  - One server for the **Web Server (Nginx)**
  - One server for the **Application Server** and **Database (MySQL)**
- **Load Balancer (HAProxy)** configured in a cluster for high availability and traffic distribution
- **Web Server** serving static content and forwarding requests to the application server
- **Application Server** handling the business logic
- **Database (MySQL)** storing persistent data

---

### Explanation:

1. **Why add a Load Balancer?**  
   The load balancer distributes incoming traffic across multiple servers to prevent any single server from becoming a bottleneck or single point of failure. Configuring it in a cluster ensures high availability.

2. **Why separate Web Server and Application Server?**  
   Separating the web server from the application server improves performance by offloading static content delivery to the web server while the application server handles dynamic processing.

3. **Why use separate servers for each component?**  
   This separation allows independent scaling, better fault isolation, and improved security.

4. **How does the Load Balancer cluster work?**  
   The load balancers work in an active-active or active-passive setup to ensure continuous availability. They use algorithms like round-robin or least connections to distribute traffic.

---

### Application Server vs Web Server

- The **Web Server (Nginx)** manages HTTP requests, serves static files, and proxies requests to the application server.
- The **Application Server** executes business logic, handles database interactions, and generates dynamic content.

---

### Benefits of this architecture

- **Improved reliability** through load balancing and clustering
- **Better scalability** by distributing workload
- **Fault tolerance** via separated services and clustered load balancers

---

### Diagram

*(Add a diagram showing 3 servers: Load Balancer, Web Server, Application Server/Database, with arrows illustrating traffic flow)*

---

*This completes the scaled-up web infrastructure design project.*

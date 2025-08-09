# 1-distributed_web_infrastructure

### Project Overview

This project demonstrates a distributed web infrastructure design with three servers to host the website **www.foobar.com**.

---

### Infrastructure Components:

- **3 Servers**:  
  - Server 1: Load Balancer (HAProxy)  
  - Server 2: Web Server (Nginx) + Application Server  
  - Server 3: Database Server (MySQL) configured as Primary-Replica cluster  

- **Load Balancer:** HAProxy to distribute incoming traffic
- **Web Server:** Nginx handles HTTP requests and forwards them to the application server
- **Application Server:** Processes business logic and interacts with the database
- **Database:** MySQL Primary-Replica setup to ensure data availability and redundancy
- **Domain Name:** foobar.com with **www** record pointing to the load balancer IP

---

### Explanation:

1. **Why add more servers and components?**  
   To improve availability, reliability, and scalability by separating concerns and avoiding Single Point of Failure (SPOF).

2. **Load Balancer and distribution algorithm:**  
   HAProxy distributes incoming requests across the web/application servers using round-robin or least connections algorithm to balance load.

3. **Active-Active vs Active-Passive load balancing:**  
   - **Active-Active:** Multiple load balancers actively distribute traffic simultaneously (high availability).  
   - **Active-Passive:** One active load balancer handles traffic, while the other waits as a backup.

4. **Database Primary-Replica cluster:**  
   - **Primary Node:** Handles all write operations.  
   - **Replica Node:** Copies data from primary asynchronously and handles read operations for load distribution.

5. **Difference between Primary and Replica in regard to the app:**  
   The application sends write queries only to the Primary and can send read queries to Replicas to reduce load on the Primary.

---

### Issues with this infrastructure:

- **Single Point of Failure (SPOF):**  
  - Load balancer itself if not clustered.  
  - Database primary node failure can impact writes.

- **Security issues:**  
  - No firewall configured.  
  - No HTTPS for secure communication.

- **No monitoring:**  
  - Lack of system health checks and alerts.

---

### Diagram

*(Add a diagram showing Load Balancer distributing traffic to Web/App Server, and Database Primary-Replica)*

---

*This completes the distributed web infrastructure design project.*

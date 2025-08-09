# 2-secured_and_monitored_web_infrastructure

### Project Overview

This project enhances the distributed web infrastructure by adding security measures and monitoring capabilities to host **www.foobar.com** reliably and securely.

---

### Infrastructure Components:

- **Load Balancer (HAProxy)** with SSL termination (HTTPS)
- **Web Server (Nginx)** and Application Server separated on different machines
- **Database (MySQL)** configured as Primary-Replica cluster
- **Firewall** to restrict unauthorized access
- **Monitoring Tools** (e.g., Prometheus, Grafana, or other monitoring agents)

---

### Explanation:

1. **Why add security components?**  
   To protect the infrastructure from unauthorized access, data breaches, and to secure communication between clients and servers using HTTPS.

2. **SSL/TLS on Load Balancer:**  
   Terminate HTTPS at the load balancer to encrypt traffic between users and the infrastructure, ensuring data confidentiality and integrity.

3. **Firewall:**  
   Configured to allow only necessary ports (e.g., 80, 443 for HTTP/HTTPS, 3306 for MySQL internally) and block unwanted traffic.

4. **Monitoring:**  
   Implements system and application monitoring to track server health, resource usage, and alerts on failures or anomalies.

---

### Issues addressed with this infrastructure:

- **Improved Security:**  
  Encryption of data in transit and restricted access via firewall.

- **Reduced Risk of Downtime:**  
  Monitoring enables quick detection and response to failures.

---

### Remaining Issues:

- **Potential SPOFs:**  
  If load balancer or monitoring system is not redundant.

- **Scaling limitations:**  
  Additional scaling might be needed as traffic grows.

---

### Diagram

*(Include architecture diagram showing load balancer with HTTPS, firewall, monitored servers, and database cluster)*

---

*This completes the secured and monitored web infrastructure design project.*

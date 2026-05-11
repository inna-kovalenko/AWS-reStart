# Amazon Route 53 Failover Routing
**Primary Domain:** Networking & Content Delivery
**Key Concepts:** DNS Failover, Health Monitoring, High Availability (HA)

---

### OVERVIEW
In this project, I configured a resilient DNS strategy to ensure high availability for a web application across multiple Availability Zones. By leveraging **Amazon Route 53**, I implemented a failover routing policy that automatically redirects traffic from a primary server to a standby secondary server during an outage, minimizing downtime and maintaining business continuity.



### CORE MILESTONES

#### 1. Infrastructure Audit & Cross-Zone Verification
* **Resource Assessment:** Verified two EC2 instances (CafeInstance1 and CafeInstance2) deployed in separate Availability Zones (`us-west-2a` and `us-west-2b`).
* **Baseline Confirmation:** Validated that both endpoints were independently serving the Café application, ensuring the secondary site was ready to handle production traffic.

#### 2. Configuring Route 53 Health Checks
* **Endpoint Monitoring:** Created a health check for the primary instance's IP address, specifically targeting the `/cafe` path.
* **Aggressive Detection:** Configured a **Fast (10s)** request interval and a **Failure Threshold of 2**, enabling the system to detect an outage and initiate failover within 20 seconds.
* **Automated Alerting:** Integrated an **SNS Topic** to trigger immediate email notifications upon any status change from "Healthy" to "Unhealthy."

#### 3. Establishing DNS Failover Records
* **Primary A-Record:** Provisioned a Failover-type record for the application domain, linking it to the active Health Check with a low **TTL (15s)** for rapid DNS propagation.
* **Secondary A-Record:** Configured the standby record pointing to the secondary Availability Zone, completing the disaster recovery path.

#### 4. Validating Failover & Disaster Recovery
* **Simulated Outage:** Manually stopped the primary instance to trigger a real-world failure scenario.
* **Failover Execution:** Monitored the Route 53 dashboard as the health status transitioned to **Unhealthy**, successfully forcing the DNS to resolve to the secondary instance.
* **End-to-End Success:** Verified that the application remained accessible through the custom domain, with server information confirming traffic was now being served from the alternate Availability Zone.

---

### TECH STACK & COMPONENTS
* **DNS Management:** Amazon Route 53 (Hosted Zones, Failover Routing)
* **Monitoring & Alerting:** Route 53 Health Checks, Amazon SNS
* **Compute:** Amazon EC2 (Multi-AZ Linux nodes)
* **Application:** LAMP Stack (Apache, MariaDB, PHP)

### BUSINESS IMPACT
This lab demonstrates the ability to architect self-healing networking solutions that protect against localized infrastructure failures. By automating the DNS failover process, I eliminated the need for manual intervention during a server crash, achieving a significantly lower **Recovery Time Objective (RTO)** and ensuring a seamless experience for end-users.

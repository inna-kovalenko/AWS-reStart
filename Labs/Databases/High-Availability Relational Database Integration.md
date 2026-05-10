# High-Availability Relational Database Integration

## Lab Overview
I architected and deployed a highly available, scalable relational database using **Amazon RDS (MySQL)**. This project focused on creating a secure, multi-tier environment where a web application communicates with a private backend database replicated across multiple data centers.

## Key Achievements & Technical Milestones

### 1. Secure Tiered Networking
* **Security Group Chaining:** Engineered a **DB Security Group** that uses "Source Security Group" referencing. Instead of opening ports to the whole world, I restricted database access (Port 3306) specifically to instances belonging to the **Web Security Group**.

This demonstrates completion of the step above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c33be37b-6afb-4b68-b5a9-c2371f146f97" />

* **DB Subnet Group Configuration:** Defined a **Subnet Group** spanning two separate Availability Zones. This ensures the database has a "landing zone" in multiple physical locations for failover purposes.

This shows the Subnet Group was successfully created:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/31623d4a-0e54-4833-ba84-415b77acfcc7" />


### 2. Multi-AZ Production Deployment
* **Engine Selection:** Provisioned a **MySQL 8.x** instance using the **db.t3.medium** burstable class.
* **High Availability (HA):** Implemented a **Multi-AZ Deployment**, where AWS automatically maintains a synchronous standby replica in a different AZ to ensure data durability and minimize downtime during maintenance or outages.
* **Storage Optimization:** Utilized **General Purpose SSD (gp3)** storage to balance cost and performance for the relational workload.

Here is the screen with details about the newly created Database with the Endpoint information selected for use in the next steps:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1133f1b6-5b55-4cb7-b1c9-3f148e1a3f69" />

### 3. Application-Database Integration
* **Endpoint Orchestration:** Successfully linked a live Web Application to the RDS instance by configuring the **DB Endpoint**, credentials, and schema name (`lab`).
* **CRUD Functional Testing:** Validated end-to-end data persistence by performing Create, Read, Update, and Delete (CRUD) operations via the web interface, confirming the application could successfully write to and retrieve from the RDS backend.

---
**Tech Stack:** Amazon RDS (MySQL), VPC (Security Groups, Subnets), Multi-AZ Failover, EC2, Web Application Integration.

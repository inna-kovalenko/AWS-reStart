# High-Performance Database Orchestration with Amazon Aurora

## Lab Overview
I architected and deployed an **Amazon Aurora (MySQL Compatible)** database cluster to manage a global dataset. This project involved configuring a secure, private database backend and establishing a secure administrative path via an Amazon EC2 "Command Host."

## Key Achievements & Technical Milestones

### 1. Enterprise Database Provisioning
* **Aurora Cluster Architecture:** Provisioned a MySQL-compatible Aurora cluster with a focus on developer-grade performance using the **db.t3.medium** instance class.
* **Network & Security Isolation:** * Deployed the database within a **LabVPC** and a dedicated **DB Subnet Group**.
    * Enforced **Private Access**, ensuring the database was not reachable via the public internet.
    * Utilized **Security Group Chaining** to authorize only the "Command Host" to communicate with the database on Port 3306.

### 2. Secure Administrative Access
* **SSM Session Manager:** Connected to a Linux-based **Command Host** (EC2) without needing a public IP or open SSH ports, utilizing AWS Systems Manager for a higher security posture.
* **Client Configuration:** Installed and configured the **MariaDB client** utility to serve as the SQL shell for cluster interaction.

### 3. Database Engineering & SQL Proficiency
* **Endpoint Management:** Identified and utilized the **Cluster (Writer) Endpoint** to ensure high availability and automatic failover support for write operations.
* **Schema Development:** * Created a complex relational table (`country`) with specific data types including `ENUM`, `FLOAT`, and `SMALLINT`.
    * Performed data ingestion of international records and executed filtered **SQL SELECT queries** to validate data integrity.
* **Query Optimization:** Successfully retrieved targeted records based on multi-variable logic (Population and GNP metrics), demonstrating the ability to extract actionable insights from raw data.

---
**Tech Stack:** Amazon Aurora (MySQL), Amazon EC2, AWS Systems Manager (SSM), MariaDB Client, SQL, VPC Networking.

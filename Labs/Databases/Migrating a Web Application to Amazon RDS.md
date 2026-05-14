# Migrating a Web Application to Amazon RDS

## Lab Overview
This project involved the migration of a live café web application from a local standalone database—hosted on a LAMP stack EC2 instance—to a fully managed Amazon Relational Database Service (RDS) instance. The migration focuses on improving scalability, availability, and administrative efficiency.

## Objectives
* **Infrastructure Provisioning:** Utilized the AWS Command Line Interface (CLI) to provision a MariaDB RDS instance.
* **Data Migration:** Executed a live migration from an EC2-hosted database to Amazon RDS using the mysqldump utility.
* **Network & Security:** Configured private subnets across multiple Availability Zones and implemented security group rules to enforce least-privileged access.
* **Systems Integration:** Leveraged AWS Systems Manager Parameter Store to redirect application traffic to the new RDS endpoint.
* **Observability:** Analyzed database performance and connectivity metrics using Amazon CloudWatch.

---

## Technical Milestone Summary

### 1. Baseline Data Generation
Initial orders were placed on the active café website to populate the local database. This established a verifiable dataset used to confirm the integrity of the migration upon completion.

### 2. Infrastructure as Code (CLI) Implementation
Foundational networking for the managed database was established through the following CLI operations:
* **Security Configuration:** Created the CafeDatabaseSG to restrict inbound traffic to port 3306 exclusively from the web server.
* **Subnet Architecture:** Defined a DB Subnet Group spanning two private subnets to support high-availability requirements.
* **RDS Deployment:** Launched a db.t3.micro MariaDB instance with automated backups and mandatory SSL/TLS encryption.

### 3. Migration Strategy and Execution
A structured path was followed to ensure zero data loss during the transition:
* **Extraction:** Generated a logical backup (cafedb-backup.sql) using the mysqldump utility.
* **Security Handshake:** Integrated the RDS Global Bundle CA certificate to facilitate encrypted connections.
* **Ingestion:** Restored the SQL backup to the RDS endpoint and validated record counts to ensure data consistency.

### 4. Configuration Management
To align with cloud-native best practices, database connection strings were externalized. By updating the /cafe/dbUrl parameter in the AWS Systems Manager Parameter Store, the application successfully transitioned to the RDS instance without requiring code-level modifications.

### 5. Performance Monitoring
Post-migration stability was verified through the RDS Monitoring interface. Real-time tracking of DatabaseConnections and CPUUtilization confirmed that the managed instance was correctly handling application workloads and administrative queries.

---

## Technical Skills Demonstrated
* **Cloud Architecture:** Multi-AZ Subnet Design, VPC Security, High Availability.
* **Database Administration:** Schema Migration, MariaDB/MySQL CLI, SSL/TLS Encryption, DML/DDL.
* **AWS Services:** Amazon RDS, EC2, Systems Manager (Parameter Store), Amazon CloudWatch.
* **Systems Administration:** Bash scripting, secure tunneling, and environment troubleshooting.

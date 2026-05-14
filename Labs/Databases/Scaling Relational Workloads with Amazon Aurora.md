# AWS Technical Synopsis: Scaling Relational Workloads with Amazon Aurora

### **Strategic Overview**
Architected and deployed a high-performance, MySQL-compatible **Amazon Aurora** cluster to evaluate its efficiency and reliability within a distributed cloud environment. This project focused on implementing secure, tiered networking and validating the serverless-ready database engine against complex relational queries.

---

### **Technical Executions**

*   **Engineered Scalable Database Infrastructure**: 
    *   Provisioned a **high-availability (Multi-AZ-ready)** Amazon Aurora cluster via Amazon RDS.
    *   Optimized performance using **db.t3.medium burstable instances** to balance cost-efficiency with high-load handling.
*   **Implemented Network Hardening & Secure Access**: 
    *   Isolated database resources within a custom **Virtual Private Cloud (VPC)** using private subnet groups.
    *   Managed granular ingress control through **DBSecurityGroup** rules, adhering to the principle of least privilege.
    *   Established secure, encrypted administrative tunnels via **AWS Systems Manager Session Manager**, bypassing the need for public-facing SSH exposure.
*   **Database Management & DDL/DML Operations**: 
    *   Configured an **Amazon EC2 Linux host** as a dedicated management node, installing and tuning the **MariaDB client** for remote cluster interaction.
    *   Executed advanced Data Definition Language (DDL) scripts to build normalized schemas with constrained data types.
    *   Facilitated data ingestion and validated the **Aurora Writer Endpoint** through multi-record insertion scripts.
*   **Optimized Query Performance**: 
    *   Validated the cluster's indexing and retrieval capabilities by executing filtered SQL queries on high-cardinality datasets.
    *   Confirmed low-latency response times for complex analytical operations involving multi-variable filters.

---

### **Architecture Stack**
*   **Cloud Engine**: Amazon Aurora (MySQL 8.0)
*   **Compute Gateway**: Amazon EC2 & AWS Systems Manager
*   **Network Fabric**: Amazon VPC, DB Subnet Groups, Security Groups
*   **Client Interface**: MariaDB / MySQL Shell

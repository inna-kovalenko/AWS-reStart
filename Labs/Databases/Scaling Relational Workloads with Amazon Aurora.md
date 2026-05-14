# AWS Technical Synopsis: Scaling Relational Workloads with Amazon Aurora

### **Strategic Overview**
Architected and deployed a high-performance, MySQL-compatible **Amazon Aurora** cluster to evaluate its efficiency and reliability within a distributed cloud environment. This project focused on implementing secure, tiered networking and validating the serverless-ready database engine against complex relational queries.

---

### **Technical Executions**

*   **Engineered Scalable Database Infrastructure, Implementing Network Hardening & Secure Access**: 
   
   *   Optimized performance using **db.t3.medium burstable instances** to balance cost-efficiency with high-load handling.

This shows selection of the **Instance Class**:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/de735275-c913-497e-b845-a4eb55f67263" />

 *   Provisioned a standalone Amazon Aurora DB cluster optimized for development and testing environments.

The screenshot demonstrates I chose a cost-optimized, single-node Amazon Aurora cluster, with the underlying architecture ready to scale to a High-Availability (Multi-AZ) production environment:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/060330b2-36f4-4825-b71e-718a33a49418" />

The image above also shows completion of the steps below:

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

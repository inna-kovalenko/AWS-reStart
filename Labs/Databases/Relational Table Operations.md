# Relational Table Operations

This lab focused on the lifecycle of a relational database, incl. management of schemas and tables via the MySQL command-line interface. I performed end-to-end operations from establishing secure connections to decommissioning resources.

---

### **Technical Objectives**
*   **Secure Access**: Established a remote connection to a Linux Command Host via AWS Systems Manager.
*   **Schema Design**: Constructed a `world` database and defined a multi-attribute `country` table using SQL data types.
*   **Structural Refinement**: Applied `ALTER` statements to modify existing table structures and fix naming errors without impacting data integrity.
*   **Environment Decommissioning**: Executed precise `DROP` sequences to safely remove resources and verify successful deletion.

---

### **Implementation Steps**

#### **1. Database Connectivity**
To interface with the relational engine, I navigated the Linux environment and initiated the MySQL client:
```bash
# Elevate privileges and navigate to the home directory
sudo su
cd /home/ec2-user/

# Access the MySQL shell
mysql -u root --password='re:St@rt!9'

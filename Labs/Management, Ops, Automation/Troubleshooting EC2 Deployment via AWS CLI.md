# Troubleshooting EC2 Deployment via AWS CLI

**Primary Domain:** Ops / Management / Automation  


**Key Concepts:** Infrastructure as Code (IaC), CLI Debugging, LAMP Stack

---

### ACTIVITY OVERVIEW
In this project, I moved beyond the AWS Management Console to launch and manage resources using the **AWS Command Line Interface (CLI)**. The core challenge involved executing a complex deployment script for a **LAMP Stack** (Linux, Apache, MariaDB, PHP), identifying intentional configuration errors, and using professional Linux diagnostic tools to bring the application to a "Healthy" state.



### CORE MILESTONES & STEP-BY-STEP ACHIEVEMENTS

#### 1. CLI Host Configuration
* **Environment Setup:** Established a secure connection to a dedicated CLI Host and initialized the AWS environment using `aws configure`.
* **Parameter Mapping:** Programmatically mapped Access Keys, Secret Keys, and Regional settings to ensure the CLI could interact with the Cafe VPC architecture.

#### 2. Automated Instance Provisioning
* **Scripted Infrastructure:** Analyzed and executed a Bash script designed to automate the discovery of VPC IDs and Subnet IDs, followed by the creation of a "cafeserver" instance.
* **Bootstrapping with User Data:** Configured an automated **User Data** script to install the web server, relational database, and PHP components during the initial boot sequence.

#### 3. Systematic Troubleshooting (The Challenge)
* **Resolving AMI Mismatches:** Identified an `InvalidAMIID.NotFound` error; debugged the script to ensure the Amazon Machine Image ID aligned with the specific lab region.
* **Network Audit via nmap:** When the web server failed to load, I installed and utilized the **nmap** utility to scan for open ports.
* **Security Group Hardening:** Identified a closed Port 80 through the scan and updated the Security Group rules to permit inbound HTTP traffic.

#### 4. Operational Validation
* **Log Analysis:** Monitored the `cloud-init-output.log` file in real-time to verify that the MariaDB database scripts and PHP configurations were executed without errors.
* **End-to-End Testing:** Validated the functionality of the **Café Web Application** by successfully placing orders and retrieving data from the persistent MariaDB storage.

---

### TECH STACK & COMPONENTS
* **Compute:** Amazon EC2 (t3.small)
* **Automation:** AWS CLI, Bash Scripting, User Data
* **Operating System:** Amazon Linux 2023
* **Diagnostics:** nmap, Cloud-init logs, VI Editor
* **Database:** MariaDB (MySQL fork)

### BUSINESS IMPACT
This lab demonstrates the ability to manage cloud infrastructure at scale by moving away from manual UI tasks toward **Automation and Scripting**. By successfully troubleshooting CLI-level errors and performing network audits, I’ve proven my capability to handle the "Ops" side of Cloud Architecture—ensuring that automated deployments are not only fast but also secure and functional.

# Hybrid EC2 Deployment (Console & CLI Orchestration)

## Lab Overview
I executed a multi-tier deployment strategy to launch and manage Amazon EC2 instances. This lab focused on the dual approach of manual provisioning via the AWS Management Console and automated orchestration using the AWS Command Line Interface (CLI).

Here is the breakdown of the task with visualisation of the corresponding architecture:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/15a6768b-f451-40ed-8b32-e78bbaf091c1" />


## Key Achievements & Technical Milestones

### 1. Bastion Host Architecture (Manual Provisioning)
* **Infrastructure Setup:** Provisioned a "Bastion Host" using the **Amazon Linux 2 AMI** and a **t3.micro** instance type.
* **Network Isolation:** Launched the instance within a dedicated **Lab VPC** and a Public Subnet, ensuring a secure entry point for administrative tasks.
* **Identity & Access Management:** Attached a specialized **IAM Instance Profile (Bastion-Role)** to the host, granting the instance secure, credential-less permission to call other AWS services.

### 2. Automated Web Tier Deployment (AWS CLI)
* **Programmatic Resource Discovery:** Used CLI commands to dynamically retrieve environment-specific metadata, including:
    * **Latest AMI ID** via AWS Systems Manager Parameter Store.
    * **Subnet & Security Group IDs** using `describe-subnets` and `describe-security-groups` filters.
* **Bootstrapping at Scale:** Launched the "Web Server" instance using the `run-instances` command, injecting a **User Data script** to automate the installation of the Apache web server and application files.
* **State Monitoring:** Utilized `aws ec2 wait` and `describe-instances` with JSON queries to programmatically verify instance readiness.

### 3. Secure Administration
* **Agentless Connectivity:** Leveraged **EC2 Instance Connect** for secure, browser-based shell access to the Bastion host, eliminating the need for local SSH key management.
* **Verification:** Successfully validated the end-to-end deployment by accessing the Web Server's **Public DNS** name, confirming the automated web stack was fully operational.

---
**Tech Stack:** AWS CLI, Amazon EC2, Amazon Linux 2, IAM Roles, AWS Systems Manager (Parameter Store), Bash Scripting.

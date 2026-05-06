# VPC and Web Server Infrastructure Deployment

## Lab Overview
I successfully designed and deployed a custom, high-availability virtual network environment on AWS to support a web application. This project involved building a Virtual Private Cloud (VPC) from scratch, configuring multi-layered security protocols, and automating a web server deployment.

This visualizes the task to create a VPC with additional components to produce a customized network for a Fortune 100 customer:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8365a9c5-8e0b-4577-9f36-317fbe49575d" />

## Key Achievements & Technical Milestones

### 1. Custom VPC Architecture
*   Designed and implemented a **Virtual Private Cloud (VPC)** with a `10.0.0.0/16` CIDR block.

This demonstrates completion of the step above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b81125e8-5ee0-4093-ac2a-64b4aeab3f20" />

*   Provisioned a multi-tier network spanning two **Availability Zones** to ensure high availability.
*   Configured **Public Subnets** for web traffic and **Private Subnets** for backend resources.
*   Deployed a **NAT Gateway** to allow secure outbound internet connectivity for private resources.

### 2. Network Routing & Connectivity
*   Established an **Internet Gateway (IGW)** to provide public internet access to the VPC.
*   Created and managed **Route Tables**, specifically mapping `0.0.0.0/0` traffic to the IGW for public-facing subnets.
*   Executed manual **Subnet Associations** to ensure correct traffic flow across the custom architecture.

### 3. Security & Infrastructure Hardening
*   Engineered a **Security Group** strategy acting as an instance-level firewall.
*   Configured **Stateful** inbound rules to permit HTTP (Port 80) and ICMP traffic from any IPv4 source (`0.0.0.0/0`).
*   Verified **Network ACLs (NACLs)** at the subnet level to provide a second layer of stateless defense.

### 4. Automated Server Deployment
*   Launched an **Amazon EC2 (t3.micro)** instance into a public subnet.
*   Automated the installation and configuration of the **Apache Web Server (httpd)**, PHP, and MySQL using a **Bash User Data script**.
*   Successfully deployed the web application files and verified live connectivity via the **Public IPv4 DNS**.

---
**Tech Stack:** AWS (VPC, EC2, IGW, NAT Gateway), Linux (Amazon Linux 2), Bash Scripting, Apache.

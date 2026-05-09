# Full-Stack Infrastructure Deployment on Amazon EC2

## Lab Overview
I architected and deployed a functional web server environment from scratch on AWS. This project involved configuring the underlying networking layers, provisioning compute resources, and automating software installation to host a custom web application.

## Key Achievements & Technical Milestones

### 1. Networking & Virtual Private Cloud (VPC) Architecture
* **Virtual Network Construction:** Designed a custom **VPC** and **Subnet** to isolate compute resources.
* **Internet Connectivity:** Configured an **Internet Gateway (IGW)** and modified **Route Tables** to enable bidirectional traffic between the instance and the public internet.
* **Security Governance:** Engineered a **Security Group** acting as a virtual firewall, specifically authorizing inbound traffic for **SSH (Port 22)** and **HTTP (Port 80)**.

### 2. Compute Provisioning & Automation
* **Instance Specification:** Launched an Amazon Linux instance using a **T3.micro** (or smaller) instance type to optimize performance and cost.
* **Bootstrapping with User Data:** Automated the deployment process by injecting a shell script into the **User Data** field to:
    * Install the **Apache (httpd)** web server.
    * Initialize the service automatically upon boot.
    * Configure directory permissions (`/var/www/html`) to allow web content management.
* **Storage Configuration:** Provisioned a **General Purpose SSD (gp2)** root volume for reliable, low-latency block storage.

### 3. Application Deployment & System Validation
* **Secure Access:** Utilized **EC2 Instance Connect** for browser-based SSH access, maintaining a high security posture without needing local key management.
* **Content Engineering:** Developed and deployed a custom HTML project page using Linux CLI tools (elevated via `sudo`) to the web root.
* **System Auditing:** Verified successful service installation by analyzing the **EC2 System Log**, ensuring all bootstrapping scripts executed without failure.

---
**Tech Stack:** AWS EC2, VPC, Route Tables, Internet Gateway, Security Groups, Apache (httpd), Bash Scripting, HTML.

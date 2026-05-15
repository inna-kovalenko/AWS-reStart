# Infrastructure Deployment: Automated Web Architecture on Amazon EC2

## Executive Summary
This lab demonstrates the implementation of a scalable web tier within a custom-architected VPC. By leveraging **EC2 User Data** for automated provisioning and strict **Security Group** orchestration, I established a functional Apache environment on Amazon Linux, ensuring high availability through proper **Internet Gateway (IGW)** routing and public subnet mapping.

---

## Technical Architecture & Implementation

### 1. Networking & Security Perimeter
*   **VPC Design:** Provisioned a dedicated VPC environment with a custom IPv4 CIDR block.
*   **Routing Logic:** Integrated an **Internet Gateway** and updated **Route Tables** to enable bidirectional traffic for public-facing resources.
*   **Traffic Control:** Engineered a stateful Security Group implementing the principle of least privilege, specifically authorizing:
    *   **TCP 80:** Global ingress for web traffic.
    *   **TCP 22:** Scoped ingress for administrative maintenance via **EC2 Instance Connect**.

### 2. Automated Provisioning (Bootstrap)
To eliminate manual configuration drift, I utilized a bash-based **Bootstrap Script** within the EC2 metadata (User Data). This automated:
*   Yum repository updates and **Apache (httpd)** binaries installation.
*   Systemd service persistence across reboots.
*   Recursive permission hardening (`chmod 2775`) and ownership assignment for the `/var/www` directory to facilitate secure content deployment.

### 3. Storage & Compute Scaling
*   **Compute:** Optimized resource allocation using the **T3 instance family**, leveraging burstable performance for variable web workloads.
*   **Storage:** Provisioned an **EBS Root Volume (gp2)**, balancing IOPS and throughput for consistent boot performance and application responsiveness.

---

## Key Achievements
*   **Zero-Touch Deployment:** Verified successful service initialization via **CloudWatch/System Logs** analysis.
*   **End-to-End Connectivity:** Validated the full stack by deploying a production-ready HTML landing page accessible via the instance’s Elastic/Public IP.
*   **Cloud Governance:** Adhered to AWS best practices for AMI selection and instance rightsizing.

# Infrastructure Deployment: Automated Web Architecture on Amazon EC2

## Executive Summary
This lab demonstrates the implementation of a scalable web tier within a custom-architected VPC. By leveraging **EC2 User Data** for automated provisioning and strict **Security Group** orchestration, I established a functional Apache environment on Amazon Linux, ensuring high availability through proper **Internet Gateway (IGW)** routing and public subnet mapping.

---

## Technical Architecture & Implementation

### 1. Networking & Security Perimeter
*   **VPC Design:** Provisioned a dedicated VPC in us-west-2 (Oregon) with a custom IPv4 CIDR block and an Internet Gateway for external connectivity.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4d4d8c0d-ce09-4535-87e1-cc290244f4bf" />

*   **Routing Logic:** Integrated an **Internet Gateway** and updated **Route Tables** to enable bidirectional traffic for public-facing resources.
*   **Traffic Control:** Engineered a stateful Security Group implementing the principle of least privilege, specifically authorizing:
    *   **TCP 80:** Global ingress for web traffic.
    *   **TCP 22:** Administrative ingress for maintenance via **EC2 Instance Connect**.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b19d9970-44eb-432d-b207-244f97d2462d" />

> The instance was provisioned in a Public Subnet with a Public IPv4 address (18.236.124.24) and an attached Security Group configured to handle both web traffic and remote management.

### 2. Post-Deployment Configuration & Content Delivery

To finalize the web service, I accessed the instance via **EC2 Instance Connect** and utilized a **Heredoc (EOF)** to programmatically generate the `projects.html` file. This CLI-based approach ensured the landing page was deployed to the Apache root directory (`/var/www/html/`) with precision and speed, avoiding the overhead of manual text editors.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/42d57820-3cc6-4a05-a98f-5ade9d065bc0" />

### 3. Environment Specifications & Final Result

To optimize for the web workload, the instance was provisioned using the **T3 family** with an **8 GiB gp2 EBS root volume**, ensuring a balance of burstable compute power and consistent storage throughput.

| Resource | Specification | Purpose |
| :--- | :--- | :--- |
| **Instance Type** | t3.micro | Burstable performance for web workloads. |
| **Root Volume** | 8 GiB (gp2) | Balanced IOPS and throughput for the OS. |
| **Deployment URL** | `http://18.236.124.24/projects.html` | Verified production path (Lab Environment). |

> **Note on Connectivity:** The URL above reflects the specific path created via the CLI. While the Public IP is ephemeral and released upon lab termination, the screenshot below confirms successful content delivery at this address.

---
## Final Project Outcome

* **Website URL:** `http://18.236.124.24/projects.html`
* **Success:** Verified the web server is live and correctly displaying the custom HTML content.
* **Automation:** The bootstrap process successfully reduced manual configuration time to zero.


# AWS Technical Case Study: Troubleshooting EC2 Deployment via AWS CLI

## Overview
This lab involved the deployment of a functional LAMP Stack (Linux, Apache, MariaDB, PHP) on an Amazon EC2 instance using the AWS Command Line Interface (AWS CLI). The primary objective was to debug a legacy deployment script to successfully host the Café Web Application.

---

## Technical Objectives
* **CLI-Driven Orchestration:** Establish and configure AWS CLI credentials to manage infrastructure remotely.
* **LAMP Stack Deployment:** Provision a multi-tier application environment using automated User Data bootstrap scripts.
* **Infrastructure Auditing:** Resolve script-level errors and network configuration issues using system logs and industry-standard utilities.

---

## Troubleshooting Methodology

### 1. Environment Configuration
* Established a secure administrative connection via EC2 Instance Connect.
* Initialized the AWS CLI environment using `aws configure` to define regional parameters and output formats.

### 2. Script Debugging and Logic Correction

* **Issue #1: Invalid AMI ID Syntax**
    * **Diagnosis:** The script failed with `InvalidAMIID.NotFound` because brackets `[]` were accidentally included in the `imageId` variable.
    * **Resolution:** Used a `cat <<EOF` (Heredoc) to completely overwrite `create-lamp-instance-v2.sh` with clean variables, ensuring the `imageId` was assigned as a pure string.
* **Current Status:** Security group `sg-027776299600c1a3a` successfully created; awaiting instance launch confirmation.

This shows the **AWS CLI** environment with congigured parameters & the error message after running the above command:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ac6737c8-f866-4108-90fd-4ce0cf4b007c" />

### Technical Evidence: CLI Troubleshooting Flow
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/04318ff6-2aa1-4590-b609-df0d40ebc8c3" />

> Terminal log demonstrating the identification of InvalidAMIID errors and the subsequent resource cleanup process.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/39b1748c-a5a5-4e5f-9378-159e993312ab" />

* **Issue #2: Connectivity and Security Group Validation**
  * **Diagnosis:** The EC2 instance reached a 'Running' state, but the web application remained unreachable (Timeout).
  * **Validation:** Conducted a port scan via `nmap -Pn <public-ip>` which confirmed that TCP Port 80 was filtered/closed.
  * **Resolution:** Executed the `authorize-security-group-ingress` CLI command to programmatically open Port 80, enabling public HTTP access to the Café application.

### 3. Log Verification
* Performed real-time log analysis using `sudo tail -f /var/log/cloud-init-output.log`.
* Verified that the cloud-init service successfully initialized the MariaDB database and extracted application files without errors.

---

## Final Project Outcome

| Key Metric | Status | Verification Method |
| :--- | :--- | :--- |
| **Application Reachability** | Successful | Verified via `http://<public-ip>/cafe` |
| **Database Connectivity** | Functional | Confirmed through Order History submission |
| **Infrastructure Compliance** | Verified | Security Group rules validated for Port 22 and 80 |

---

## Core Competencies Demonstrated
* **AWS CLI Proficiency:** Full lifecycle management of EC2 and VPC resources via terminal.
* **Linux System Administration:** Proficient use of diagnostic tools including `vi`, `tail`, and `nmap`.
* **Technical Troubleshooting:** Systematic isolation and resolution of deployment failures and networking misconfigurations.

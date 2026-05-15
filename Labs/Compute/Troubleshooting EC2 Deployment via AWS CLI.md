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
The deployment script `create-lamp-instance-v2.sh` was audited and modified to resolve the following blockers:

* **Issue #1: Dynamic AMI Retrieval Failure**
  * **Diagnosis:** The script utilized an AWS Systems Manager (SSM) parameter to fetch the latest AMI, which returned an `InvalidAMIID.NotFound` error in the current region.
  * **Resolution:** Modified the script using the `vi` editor to hardcode a verified Amazon Machine Image ID compatible with the local region, ensuring a successful `RunInstances` operation.

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

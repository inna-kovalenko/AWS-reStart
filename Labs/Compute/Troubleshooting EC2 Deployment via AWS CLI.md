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
The deployment script `create-lamp-instance-v2.sh` was audited to resolve the following blockers:

* **Issue #1: Regional AMI Mismatch**
  * **Diagnosis:** Identified a `InvalidAMIID.NotFound` error during the `RunInstances` operation.
  * **Resolution:** Replaced the hardcoded AMI ID in the script with the verified Amazon Machine Image ID for the current deployment region.
* **Issue #2: Connectivity and Port Validation**
  * **Diagnosis:** The instance launched successfully, but the web application was unreachable via the browser.
  * **Validation:** Executed a port scan using the `nmap` utility (`nmap -Pn <public-ip>`).
  * **Resolution:** Discovered that TCP Port 80 was not exposed in the security group. Updated security group rules via CLI to permit inbound HTTP traffic.

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

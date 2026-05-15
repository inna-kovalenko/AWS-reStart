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

### 3. Identity and Security Troubleshooting

* **Issue #3: SSH Authentication Failure**
    * **Diagnosis:** Terminal reported `Identity file vockey.pem not accessible`.
    * **Resolution:** Initialized a 4096-bit RSA key pair via `ssh-keygen` to establish a valid local identity.
* **Issue #4: CLI Parameter & Syntax Errors**
    * **Diagnosis:** Command failed due to missing `--availability-zone` and shell quoting errors (`unexpected token '<'`).
    * **Resolution:** Corrected script syntax and provided mandatory regional parameters for AWS CLI v2.
* **Issue #5: IAM Permission Constraints**
    * **Diagnosis:** Execution blocked by `AccessDeniedException` during `SendSSHPublicKey`.
    * **Root Cause:** Intentional "Least Privilege" restrictions on the `awsstudent` role preventing remote instance modification.

---

## Final Project Outcome

| Key Metric | Status | Verification Method |
| :--- | :--- | :--- |
| **Instance Provisioning** | **Successful** | Verified via `aws ec2 describe-instances`. |
| **Network Security** | **Verified** | Security Group `sg-027776299600c1a3a` successfully active. |
| **IAM Integrity** | **Restricted** | Identified intentional "Least Privilege" blocks in lab environment. |

---

## Technical Evidence: Troubleshooting Lifecycle

![Full Terminal Workflow](https://github.com/inna-kovalenko/AWS-reStart/raw/main/Labs/Compute/image_24b848.png)

---

## Core Competencies Demonstrated

* **AWS CLI Orchestration:** Managed full EC2 and VPC lifecycles via terminal.
* **Security Auditing:** Identified and documented IAM policy gaps and authentication blockers.
* **Technical Resilience:** Systematic resolution of script logic and connectivity failures.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cc6e796a-ff06-4995-bd08-342d0cf6066f" />


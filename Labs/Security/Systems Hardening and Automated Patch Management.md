# Systems Hardening and Automated Patch Management

## Lab Overview
I implemented a centralized patch management solution using **AWS Systems Manager (SSM)** to automate the lifecycle of operating system updates across a hybrid fleet of EC2 instances. This project focused on establishing security baselines, managing patch groups, and ensuring cross-platform compliance for both Linux and Windows environments.

This shows an example of an available instance that Systems Manager could work with in the lab setup:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6730914e-0be7-4b22-8bc4-a7640882b47b" />


## Key Achievements & Technical Milestones

### 1. Automated Linux Patching via Default Baselines
*   Utilized **AWS Systems Manager Patch Manager** to execute fleet-wide scans and installations of critical updates for Linux instances.
*   Leveraged **Default Patch Baselines** to rapidly address vulnerabilities without the need for manual script intervention.
*   Orchestrated targeted patching operations using **Instance Tags** (e.g., `Patch Group: LinuxProd`) to ensure only specific production nodes were modified.

This demonstrates setting up the Patch function:
<img width="934" height="505" alt="image" src="https://github.com/user-attachments/assets/7a04b435-09fa-4989-8861-2e9366e85328" />


### 2. Custom Security Baseline Engineering for Windows
*   Engineered a **Custom Patch Baseline** specifically for Windows Server 2019 to enforce a strict security posture.
*   Defined granular **Approval Rules** based on Classification (Security Updates) and Severity (Critical and Important).
*   Implemented an **Auto-approval Delay** of 3 days to balance the need for rapid patching with the requirement for environmental stability.

The example of this granularity mentioned in the steps above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c786ad26-06fa-4692-ae00-bc985750a36e" />


### 3. Patch Group Management & Orchestration
*   Configured **Patch Groups** to associate specific EC2 instances with designated security baselines, preventing "configuration drift" across the fleet.

This shows progress monitoring and visualisation of patching and installing on the 3 instances:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b0630577-3535-4e52-8978-30f841270320" />

*   Automated the **Scan and Install** workflow using the `AWS-RunPatchBaseline` SSM document.
*   Managed instance reboot behaviors during maintenance windows to minimize downtime while ensuring kernel-level updates were successfully applied.

### 4. Compliance Auditing & Verification
*   Monitored the **SSM Compliance Dashboard** to verify that 100% of the managed fleet (6/6 instances) met the defined security standards.
*   Evaluated **Detailed Compliance Reports** to audit non-compliant counts and confirm the installation history of specific patches.
*   Utilized **Fleet Manager** to inspect individual node states and validate IAM role permissions required for SSM agent communication.

---
**Tech Stack:** AWS Systems Manager (Patch Manager, Fleet Manager, Run Command), EC2, IAM, Windows Server, Amazon Linux 2.

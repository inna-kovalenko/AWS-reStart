# Working with AWS CloudTrail

---


> Engineered a comprehensive security audit and remediation workflow using AWS CloudTrail and Amazon Athena to identify and neutralize a multi-vector security breach on an EC2-hosted web application.


**Primary Domain:** Security, Identity, & Compliance  

Domain: Infrastructure Security & Governance


**Key Concepts:** Governance, Compliance, Operational Auditing, Log Analysis  

---

### OVERVIEW
In this activity, I acted as a security analyst to investigate a compromised environment at the Café. I implemented **AWS CloudTrail** to establish an audit trail, analyzed logs to identify unauthorized modifications to security groups, and executed a multi-layered remediation strategy to secure both the AWS account and the underlying EC2 infrastructure.

### CORE MILESTONES

#### 1. Environment Baseline & Initial Audit
* **Security Group Configuration:** Modified the `WebSecurityGroup` to restrict SSH access (Port 22) specifically to a trusted IP address.
* **Service Verification:** Confirmed the Café website was functioning normally before the detection of unauthorized activity.

This shows I successfully modified the inbound security group rules to allow SSH access on port 22 and HTTP traffic on port 80 for the web server, and the **Website** reached at **Public IPv4 address** looked normal:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5a0d28cc-c072-4881-8b09-43c933999391" />


#### 2. CloudTrail Implementation & Incident Detection
* **Audit Configuration:** Created a management trail named `monitor` to capture all account activity in a dedicated S3 bucket (`monitoring####`).
* **Threat Identification:** Detected a website defacement and identified a "security hole" where an unauthorized inbound rule allowed global SSH access (`0.0.0.0/0`).

This is where I identified a security vulnerability - an unauthorized inbound rule was added to allow SSH access on port 22 from any IP address (0.0.0.0/0):
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d706989e-f90a-4055-84a2-fbb6686efdb8" />


#### 3. Forensic Analysis via CLI & Athena
* **Linux Log Processing:** Connected to the EC2 instance via SSH and used the `grep` utility to parse downloaded JSON logs for `sourceIPAddress` and `eventName`.
* **AWS CLI Investigation:** Utilized `lookup-events` to identify the specific API calls responsible for the security group changes.
* **SQL-Based Discovery:** Created an **Amazon Athena** table to query CloudTrail logs with SQL, allowing for the rapid identification of the hacker's IAM user, source IP, and exact event timestamps.

#### 4. Remediation & System Hardening
* **Instance Recovery:** Identified and removed the unauthorized `chaos-user` from the OS and restored the original website media files.
* **Protocol Hardening:** Modified `/etc/ssh/sshd_config` to disable `PasswordAuthentication`, ensuring only key-pair authentication is permitted.
* **IAM Governance:** Permanently deleted the compromised `chaos` IAM user to prevent further unauthorized programmatic access to the AWS account.

### CONCLUSION
I successfully restored the integrity of the Café's cloud environment by combining real-time auditing with forensic query tools. This lab demonstrated proficiency in using **CloudTrail** and **Athena** to transform raw log data into actionable security intelligence.

---

### Career Alignment
* **Skills:** AWS CloudTrail, Amazon Athena (SQL), IAM Security, SSH Hardening, Linux Forensics.

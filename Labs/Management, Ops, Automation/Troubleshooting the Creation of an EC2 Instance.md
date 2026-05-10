# PROJECT: Troubleshooting EC2 Deployment via AWS CLI
**Primary Domain:** Ops & Management
**Key Concepts:** Infrastructure Automation & Troubleshooting

### TECH STACK & COMPONENTS
* **Compute:** Amazon EC2 (t3.small)
* **Stack:** LAMP (Linux, Apache, MariaDB, PHP)
* **Automation:** AWS CLI, Bash Scripting, User Data
* **Tools:** nmap, VI Editor, cloud-init logs
* **Networking:** VPC, Security Groups, Public/Private Subnets

### CORE MILESTONES
* **CLI Automation:** Configured a secure environment using `aws configure` to transition from manual console tasks to programmatic infrastructure management.
* **Scripted Provisioning:** Executed Bash scripts to automate the discovery of VPC and Subnet IDs, establishing the foundation for repeatable Infrastructure as Code (IaC).
* **Systematic Debugging:** Resolved critical `InvalidAMIID` deployment blockers by auditing regional AMI mappings and script parameters.
* **Network Hardening & Audit:** Leveraged `nmap` to perform port-level audits, successfully troubleshooting connectivity issues by opening Port 80 for web traffic.
* **Automated Bootstrapping:** Used EC2 User Data to automate the LAMP stack installation, validating the process through real-time analysis of `cloud-init` logs.

### BUSINESS IMPACT
By implementing CLI-driven troubleshooting and automation, I demonstrated the ability to reduce deployment lead times and eliminate human error. This approach ensures high application availability and consistent security configurations across multi-tier cloud environments.

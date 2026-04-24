# Centralized Operations and Automation with AWS Systems Manager (SSM)

## Project Overview
I implemented **AWS Systems Manager (SSM)** to centralize operational data and automate management tasks across a fleet of Amazon EC2 instances. This project focused on improving security and scalability by replacing manual, per-instance management with automated "Node Management" capabilities, allowing for secure access and configuration updates without exposing traditional management ports.

Visualisation of the project work assigned:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/28dc63c4-0efd-4e84-98e7-efb41b07b123" />


## Technical Accomplishments
* **Fleet Inventory Management**: Leveraged **Fleet Manager** to automate the collection of software metadata and OS configurations, creating a centralized inventory for compliance auditing across managed nodes.

This documents completion of the step above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d43811da-d870-443f-8b32-a6792d6cc880" />


* **Automated Application Deployment**: Utilized **SSM Run Command** to remotely deploy a full web stack (Apache, PHP, and the AWS SDK) across instances simultaneously, eliminating the need for manual, error-prone local script execution.
* **Dynamic Configuration Management**: Implemented **Parameter Store** to manage application-level settings. By storing a hierarchical parameter (`/dashboard/show-beta-features`), I successfully enabled "beta" features on a live application in real-time without code deployments or server restarts.
* **Secure Remote Administration**: Replaced traditional SSH/Bastion host access with **Session Manager**, establishing an encrypted, browser-based shell for instance management. This significantly reduced the attack surface by allowing the closure of inbound SSH ports while maintaining full administrative control.
* **Programmatic Infrastructure Access**: Executed AWS CLI commands within the Session Manager environment to retrieve instance metadata in JSON format, demonstrating a secure and fully auditable administrative workflow.

## Tools & Technologies
* **AWS Systems Manager Capabilities**: Fleet Manager, Run Command, Parameter Store, Session Manager.

This example shows the CLI command that can be reused outside the Management Console:
<img width="1856" height="995" alt="image" src="https://github.com/user-attachments/assets/de6b53ac-f39e-4d67-8b8f-2cb7fb9a289f" />

* **Cloud Compute**: Amazon EC2 (Amazon Linux 2023).
* **Security & Compliance**: IAM (Identity and Access Management), AWS CloudTrail.
* **Web Technologies**: Apache Web Server, PHP.

## Key Results
* **Enhanced Security**: Achieved "zero-open-ports" management, ensuring instances remain protected from external port scans while still being fully manageable.
* **Scalability**: Demonstrated the ability to perform updates and run commands on a fleet of instances at scale rather than connecting to servers one by one.
* **Operational Agility**: Used centralized configuration management to update application behavior globally in seconds, showcasing a "Dark Launch" feature capability.

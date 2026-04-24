# Installing and Configuring the AWS CLI

## Project Overview
I successfully deployed and configured the **AWS Command Line Interface (AWS CLI)** on a remote **Red Hat Enterprise Linux (RHEL)** instance. This project focused on moving beyond the Graphical User Interface (GUI) to manage cloud infrastructure programmatically, ensuring faster workflows and automation readiness.

Here is the description of the lab with the diagram depicting the underlying architecture:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c851366a-7eb3-49fa-b70b-0a387a13cdd3" />


## Technical Accomplishments
* **Remote Environment Setup**: Established a secure **SSH connection** from a Windows local machine to a Linux EC2 instance using **PuTTY** and **RSA key-pair authentication**.
* **Software Deployment**: Executed a command-line installation of the AWS CLI v2 by retrieving packages via `curl`, unzipping resources, and managing permissions with `sudo`.

This image shows successful completion of the 2 steps mentioned above: connecting via SSH & installing AWS CLI (version visible as the selected text):
<img width="1916" height="1004" alt="image" src="https://github.com/user-attachments/assets/8f0b2580-eea7-4258-b22f-2a0bc321c603" />

* **Identity & Access Integration**: Configured secure communication between the CLI and the AWS account using **Access Keys**, **Secret Keys**, and JSON output formatting.

This step is well documented here - both the secret key and unique user ID appear in the AWS Management Console (AIM) & in CLI:
<img width="1918" height="1007" alt="image" src="https://github.com/user-attachments/assets/49a21bf2-aef9-4671-9779-814587dd16dd" />

* **Programmatic Resource Management**: Audited account security by querying **IAM (Identity and Access Management)** users and policies through the terminal.
* **Data Extraction**: Leveraged advanced CLI commands to filter customer-managed policies and exported security documents into **JSON files** for documentation and auditing.

This screenshot confirms completion of the last 2 steps (includes the challenge description from the lab instructions) - achieved thanks to quering AIM users and policies through AWS CLI:
<img width="1853" height="991" alt="image" src="https://github.com/user-attachments/assets/ceffe23a-d8d7-431a-ae2f-fdcf4856e4c9" />


## Skills Demonstrated
* **Cloud Infrastructure**: AWS EC2, VPC, IAM.
* **Linux Administration**: Command line navigation, package installation, file permissions.
* **Security**: SSH protocol, Key management, IAM Policy structures.
* **Data Handling**: JSON processing and terminal output redirection.

## Key Outcomes
* **Efficiency**: Demonstrated the ability to manage AWS resources without the Management Console.
* **Accuracy**: Successfully retrieved specific policy versions and saved them as structured data files.
* **Versatility**: Showcased cross-platform competency by bridging Windows and Linux environments.

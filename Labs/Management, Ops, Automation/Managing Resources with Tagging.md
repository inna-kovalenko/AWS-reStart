# Managing Resources with Tagging

This lab focused on infrastructure automation through resource metadata. The lab demonstrated how to utilize the AWS Command Line Interface (CLI) and the AWS SDK for PHP to manage EC2 instances at scale.

---

## Lab Objectives
During this lab, the following competencies were developed:
*   **Applied and modified tags** on existing AWS resources to improve organization.
*   **Filtered and located resources** using complex tag-based queries via the CLI.
*   **Automated lifecycle events**, such as stopping and terminating instances, based on resource attributes.

---

## Technical Scenario
The environment was built within a **Lab VPC** and included a **CommandHost** pre-configured with AWS CLI tools. The infrastructure consisted of eight Linux instances categorized by a specific tagging schema:

| Tag Name | Description | Values |
| :--- | :--- | :--- |
| **Project** | Defined the specific project ownership. | `ERPSystem`, `Experiment1` |
| **Environment** | Defined the lifecycle stage of the instance. | `development`, `staging`, `production` |
| **Version** | Tracked the software iteration. | `1.0` (Initial state) |

---

## Task Summary

### 1. Advanced Querying and Tag Manipulation
The lab utilized the `--query` parameter and **JMESPath** syntax to extract specific data from JSON responses.

This screenshot, for example, demostrates the output after filtering and quering, with visible instance IDs and tags (Environment, Version):

<img width="1809" height="996" alt="image" src="https://github.com/user-attachments/assets/238cb18c-9086-41f7-acf3-c387e4f0ba4c" />

*   **Filtered Instances**: Isolated instances belonging to both the `ERPSystem` project and `development` environment.
*   **Automated Batch Updates**: Executed a Bash script (`change-resource-tags.sh`) to perform batch updates on the `Version` tag for all identified development instances.

This demonstrates completion of the last step - all the found development instances got only their version updated, automatically and in bulk:
<img width="1830" height="996" alt="image" src="https://github.com/user-attachments/assets/8905e90f-21d7-4d30-8a77-5c0c37a34ba3" />


### 2. Automated Resource Scheduling (Stopinator)
A PHP-based utility, `stopinator.php`, was introduced to interact with the AWS SDK for PHP.
*   **Cost Optimization**: Implemented measures to shut down development environments outside of business hours.
*   **Mechanism**: The script identified instances via tag-value pairs across all AWS regions and issued `StopInstances` or `StartInstances` commands.

### 3. Challenge: "Tag-or-Terminate" Policy
This section focused on automated governance and security compliance.
*   **The Policy**: Established that any instance in a private subnet lacking a mandatory `Environment` tag was non-compliant.
*   **The Execution**: A specialized PHP script (`terminate-instances.php`) identified these untagged resources and executed a `TerminateInstances` API call to mitigate risks.

---

## Infrastructure Requirements
*   **Region Control**: All operations were maintained within the pre-assigned AWS Region.
*   **Connectivity**: Secure Shell (SSH) access to the CommandHost was required for script execution and CLI operations.

# Troubleshooting AWS CloudFormation and Infrastructure as Code (IaC)

## Overview
This project focused on the deployment and management of a cloud-based web server using Infrastructure as Code (IaC). I successfully navigated real-world deployment challenges, including stack failures, manual configuration drift, and complex resource lifecycle management.

## Technical Skills and Tools
* Infrastructure as Code: AWS CloudFormation (YAML).
* Cloud Services: EC2, VPC, S3, IAM, KMS.
* CLI and Scripting: AWS CLI, JMESPath, Bash (Userdata).
* System Administration: Linux Log Analysis (cloud-init), Vim.

## Key Scenarios and Solutions

### 1. Root Cause Analysis of Stack Failures
* Problem: The CloudFormation stack failed during the WaitCondition phase and triggered an automatic rollback, deleting logs before they could be inspected.

This is how inspecting the table with progress in resource creation helped see there was something in need of troubleshooting:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/496d57f9-eec6-4272-9dc0-6dec9984868b" />

This got confirmed by running the following command:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a046c494-4f81-4d28-9d64-41c0c72b72b9" />


* Solution: Redeployed using the --on-failure DO_NOTHING flag. I SSH'd into the instance to analyze /var/log/cloud-init-output.log and identified a package naming error (http instead of httpd).

This helped to SSH into the running instance as shown here with the help of access key:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/878a1fee-0a0d-4bcc-a539-7ef67a48f1df" />

This is how it became visible that instead of `httpd` there was `http` (`yum install -y http` has an error - there is no package called `http` - the correct name for the Apache web server on Amazon Linux is `httpd`, so because the script starts with `#!/bin/bash -ex`, the `-e` flag told the instance: "If any command fails, stop everything immediately." - so since `yum install -y http` failed, the script stopped there):

<img width="1920" height="1080" alt="Screenshot 2026-05-12 222558" src="https://github.com/user-attachments/assets/810c5aa0-0d04-4b3d-9842-c2759bb5e76a" />

* Result: Corrected the template and achieved a successful CREATE_COMPLETE status.

This shows that a CloudFormation deployment failure was resolved by correcting a UserData script typo and re-creating the stack:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/da965189-5a17-4916-9834-24861719e738" />


### 2. Identifying Configuration Drift
* Problem: Manual changes were made to security group rules via the AWS Console, diverging from the template.

For example, here the Source was changed to **My IP**:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/75d61d80-2c98-431d-8c46-ac6162a5d45f" />

* Solution: Performed Drift Detection to identify the discrepancy between the live environment and the template.

This is how **Drift** was detected:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6f038c02-54a1-4c35-8d21-271e94fcc67e" />

* Result: Used the AWS CLI to extract specific property differences, maintaining the integrity of the IaC source of truth.
* 
This shows how it was possible to inspect the details of the **Drift**:
<img width="1920" height="980" alt="image" src="https://github.com/user-attachments/assets/a5dc5667-b259-427d-a753-231bcf7cb963" />


### 3. Advanced Resource Deletion (The S3 Challenge)
* Problem: The stack failed to delete because it contained an S3 bucket with active data objects.
* Solution: Implemented a targeted deletion strategy using the --retain-resources flag for the S3 bucket's Logical ID.
* Result: Successfully removed the stack infrastructure while preserving critical data in the bucket.

This demonstrates I successfully bypassed a deletion failure by using the `--retain-resources` flag to preserve the S3 bucket while fully decommissioning the rest of the stack:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/897efc62-9777-43a4-aedd-9f465e0e02f0" />


## Lessons Learned
* Fail-Fast Logic: Using the -e parameter in bash scripts ensures that errors are caught immediately during the bootstrapping process.
* Automation vs. Manual Change: Documented how manual intervention leads to inconsistent infrastructure and why drift detection is vital for security auditing.
* Lifecycle Awareness: Mastered the protection mechanisms AWS provides to prevent accidental data loss during automation.

---
*Note: This lab was completed as part of the AWS re/Start program.*

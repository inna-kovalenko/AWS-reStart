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
* Result: Corrected the template and achieved a successful CREATE_COMPLETE status.

### 2. Identifying Configuration Drift
* Problem: Manual changes were made to security group rules via the AWS Console, diverging from the template.
* Solution: Performed Drift Detection to identify the discrepancy between the live environment and the template.
* Result: Used the AWS CLI to extract specific property differences, maintaining the integrity of the IaC source of truth.

### 3. Advanced Resource Deletion (The S3 Challenge)
* Problem: The stack failed to delete because it contained an S3 bucket with active data objects.
* Solution: Implemented a targeted deletion strategy using the --retain-resources flag for the S3 bucket's Logical ID.
* Result: Successfully removed the stack infrastructure while preserving critical data in the bucket.

## Lessons Learned
* Fail-Fast Logic: Using the -e parameter in bash scripts ensures that errors are caught immediately during the bootstrapping process.
* Automation vs. Manual Change: Documented how manual intervention leads to inconsistent infrastructure and why drift detection is vital for security auditing.
* Lifecycle Awareness: Mastered the protection mechanisms AWS provides to prevent accidental data loss during automation.

---
*Note: This lab was completed as part of the AWS re/Start program.*

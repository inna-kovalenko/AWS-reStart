# Building a Serverless Sales Analysis Report System with AWS Lambda

## Lab Overview
In this project, I deployed a serverless solution using **AWS Lambda** to automate daily sales reporting. The system connects to a MySQL database running on an EC2 instance, extracts sales data, and sends a formatted report to an administrator via **Amazon SNS**.



## Architecture Components
*   **AWS Lambda**: Two functions (Data Extractor and Report Generator).
*   **Lambda Layers**: Reusable PyMySQL library for database connectivity.
*   **Amazon SNS**: Simple Notification Service for email delivery.
*   **Amazon EventBridge**: Cron-based scheduling for daily automation.
*   **AWS Systems Manager (Parameter Store)**: Secure storage for database credentials.
*   **Amazon EC2**: Hosted the café database on a LAMP stack.

Visualization of the architecture of the sales analysis report solution with the order in which actions should occur:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6a0dc7fe-4c23-469a-836e-e58c67462019" />


## Key Technical Tasks & Skills

### 1. Security & Identity (IAM)
*   Analyzed and assigned least-privilege permissions for Lambda execution roles.
*   Configured policies including `AWSLambdaVPCAccessExecutionRole` to allow the Lambda to reach resources inside a private VPC.

### 2. Efficiency with Lambda Layers
*   Created a custom **Lambda Layer** for the `PyMySQL` library. This reduced the size of the deployment package and followed best practices for code reuse.

Confirmation of successful completion of the above step:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/58b45897-e410-44b1-be8d-d5394e84b976" />

### 3. Serverless Integration & Troubleshooting
*   **Database Integration**: Configured VPC settings (Subnets/Security Groups) to bridge the serverless function with the EC2-hosted database.
*   **Testing & Debugging**: Identified a connection timeout issue. Used **CloudWatch Logs** to diagnose that the Security Group was missing an inbound rule for Port 3306 (MySQL).
*   **Automation**: Implemented a **Cron expression** in EventBridge to trigger the report at 8 PM (UTC) Monday–Saturday.

## Core Objectives Achieved
- [x] Facilitated cross-resource communication via IAM.
- [x] Managed external library dependencies using Layers.
- [x] Automated data extraction and notification workflows.
- [x] Resolved networking bottlenecks using CloudWatch and Security Group adjustments.

## Why this matters
This lab demonstrates the ability to manage the **SysOps** side of cloud computing—moving beyond simple code execution to ensuring security, connectivity, and cost-effective automation.

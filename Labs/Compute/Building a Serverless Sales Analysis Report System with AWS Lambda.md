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

Confirmation of successful completion of the above steps:

**1**
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/58b45897-e410-44b1-be8d-d5394e84b976" />

**2**
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9e660ceb-5ba7-421e-91ea-2f745c70baa7" />

**3**

Here I made sure the function expects to receive the database connection information (`dbURL`, `dbName`, `dbUser`, `dbPassword`) in the event input parameter:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c954a421-3429-43cc-9b4e-b31268ed0b58" />

### 3. Serverless Integration & Troubleshooting
*   **Database Integration**: Configured VPC settings (Subnets/Security Groups) to bridge the serverless function with the EC2-hosted database.

This shows how configuring the above settings looked like on **AWS Management Console**:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/26ef4399-60cb-4ec6-bb09-339551d9577e" />

*   **Testing & Debugging**: Identified a connection timeout issue. Used **CloudWatch Logs** to diagnose that the Security Group was missing an inbound rule for Port 3306 (MySQL).

Sample page showing the message **"Execution result: failed"**: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e86b13de-096c-4068-bcce-191694bb30eb" />

This is how I added the needed **Inbound Rule** for **Lambda**:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/000308a3-53f0-439f-9d69-f377df21c757" />

This confirms the change was made:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f3f7abca-494b-4a13-94e3-ea7adb8409a8" />

The screenshot demonstrates that during testing the body field, which contains the report data that the function extracted, was empty because there was no order data in the database:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a134a7bb-73ba-4f91-8a8b-7f204a9483f9" />

So it was logical to go to the **Cafe Website** to place an order in order to populate the **Database** as in this example:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dd7feb77-a989-478a-91b1-85351ea84bbf" />

As a result, the **Test** was successful:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bada4d21-e952-47dc-9b53-435fb012c2e9" />


*   **Automation**: Implemented a **Cron expression** in EventBridge to trigger the report at 8 PM (UTC) Monday–Saturday.

## Core Objectives Achieved
- [x] Facilitated cross-resource communication via IAM.
- [x] Managed external library dependencies using Layers.
- [x] Automated data extraction and notification workflows.
- [x] Resolved networking bottlenecks using CloudWatch and Security Group adjustments.

## Why this matters
This lab demonstrates the ability to manage the **SysOps** side of cloud computing—moving beyond simple code execution to ensuring security, connectivity, and cost-effective automation.

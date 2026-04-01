# Troubleshooting a VPC 

This lab simulates real-world cloud troubleshooting scenarios where network misconfigurations prevent application access. It is especially useful for roles in cloud engineering, DevOps, and infrastructure support.

## Overview
This lab focuses on diagnosing and resolving networking issues within an AWS Virtual Private Cloud (VPC). You will work in a pre-configured environment that includes two VPCs, Amazon EC2 instances, and supporting network components.

The lab follows a structured troubleshooting workflow, using VPC Flow Logs and AWS CLI tools to identify and fix connectivity problems affecting a web server environment.

## Architecture
- Two VPCs with associated subnets and routing
- EC2 instances (including a café web server)
- A CLI Host instance in a separate VPC for running AWS CLI commands
- Networking components such as route tables, gateways, and security configurations

<img width="1727" height="838" alt="image" src="https://github.com/user-attachments/assets/4db909ad-103a-41a5-88c3-7d4a8dee6195" />

## Tasks
1. Create an Amazon S3 bucket to store VPC Flow Log data  
2. Enable VPC Flow Logs to capture all IP traffic across network interfaces  
3. Troubleshoot VPC configuration issues to restore access to resources  
4. Download and analyze flow log data to identify root causes  

## Objectives
By completing this lab, I was able to:
- Configure and enable VPC Flow Logs  
- Identify and resolve VPC networking issues  
- Interpret and analyze flow log data for troubleshooting

## Sample Steps

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e00a6089-7e13-4fbc-afc0-0bf62a610ba5" />

<img width="1756" height="892" alt="image" src="https://github.com/user-attachments/assets/b7b33730-6c3d-412c-9d07-7db4e2d469f0" />

<img width="1859" height="894" alt="image" src="https://github.com/user-attachments/assets/ddf30526-7b7d-4d99-9c54-5e6a8833dc42" />


## Key Skills
- AWS networking fundamentals (VPC, subnets, routing)
- Troubleshooting connectivity issues
- Log analysis using VPC Flow Logs
- Working with AWS CLI for diagnostics

## Tools & Services
- Amazon VPC  
- Amazon EC2  
- Amazon S3  
- AWS CLI  

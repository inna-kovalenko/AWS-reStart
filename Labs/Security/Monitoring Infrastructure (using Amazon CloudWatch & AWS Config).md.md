# Monitoring Infrastructure with Amazon CloudWatch & AWS Config

## Project Overview
I implemented a comprehensive monitoring and compliance strategy for AWS infrastructure. This project focused on capturing system-level data, automating log analysis, and enforcing organizational standards to ensure high reliability and security across cloud resources.



## Technical Accomplishments
* **Unified Agent Deployment**: Automated the installation of the **CloudWatch Agent** across EC2 fleets using **AWS Systems Manager (SSM) Run Command**.
* **Log Analytics & Insights**: Configured the collection of web server access and error logs. Engineered **Metric Filters** using pattern matching (`[ip, id, user, timestamp, request, status_code=404, size]`) to extract actionable data from raw logs.
* **Proactive Alerting**: Established **CloudWatch Alarms** tied to **Amazon SNS (Simple Notification Service)** to trigger real-time email notifications when specific error thresholds (e.g., HTTP 404 spikes) were met.
* **Deep System Visibility**: Expanded visibility beyond standard hypervisor metrics to capture high-resolution **internal metrics** such as memory utilization, disk I/O, and swap usage.
* **Event-Driven Automation**: Designed **CloudWatch Event Rules** to detect and respond to critical resource state changes (e.g., EC2 instance stops or terminations) in near-real-time.
* **Compliance Governance**: Deployed **AWS Config** rules to enforce infrastructure standards, specifically auditing resources for mandatory tagging (`required-tags`) and identifying underutilized assets (`ec2-volume-inuse-check`).

## Tools & Technologies
* **Monitoring**: Amazon CloudWatch (Logs, Metrics, Alarms, Events).
* **Governance**: AWS Config, Systems Manager (Parameter Store, Run Command).
* **Communication**: Amazon SNS.
* **Compute**: Amazon EC2 (Linux).
* **Data Format**: JSON (for Agent configuration and Event output).

## Key Results
* **Security & Auditing**: Eliminated the need to manually SSH into servers for log review, centralizing all audit data in CloudWatch Logs.
* **Operational Efficiency**: Reduced "Mean Time to Detection" (MTTD) for application errors by implementing automated 1-minute alarm cycles.
* **Cost Optimization**: Utilized AWS Config to identify unattached EBS volumes, preventing unnecessary billing for orphaned storage resources.

# Infrastructure Monitoring and Automated Alerting

## Lab Overview
I implemented a real-time monitoring and alerting solution to detect anomalous resource behavior on Amazon EC2 instances. By integrating **Amazon CloudWatch** with **Amazon SNS**, I established an automated notification system that alerts administrators via email when CPU utilization exceeds predefined safety thresholds, simulating a response to potential malware or system compromise.

> **Security Note: Incident Detection** > While this is a Compute monitoring task, it serves as a critical **Security** control. Spikes in CPU utilization are often the first indicator of a compromised instance being used for unauthorized crypto-mining or as part of a Botnet. Establishing a 60% threshold ensures "Resource Exhaustion" attacks are detected and mitigated before they impact service availability.

## Key Achievements & Technical Milestones

### 1. Notification Infrastructure with Amazon SNS
* Provisioned an **Amazon SNS (Simple Notification Service)** topic to serve as the communication backbone for system alerts.
* Configured and validated an **Email Subscription** protocol, including end-to-end confirmation to ensure reliable delivery of incident notifications.

### 2. CloudWatch Alarm Engineering
* Established a **Metric Alarm** in Amazon CloudWatch to monitor the `CPUUtilization` metric with a 1-minute granularity for high-resolution tracking.
* Defined a static threshold of **> 60% CPU utilization** as the trigger condition for incident response.
* Linked the Alarm state to the SNS topic to automate the "A2P" (Application-to-Person) notification workflow.

### 3. Stress Testing & Incident Simulation
* Executed a manual **CPU Stress Test** on a Linux EC2 instance using the `stress` utility to simulate 100% load.
* Used terminal monitoring tools (`top`) to validate real-time resource consumption during the simulated attack.
* Verified the transition of the CloudWatch alarm from `OK` to `In Alarm` state, confirming the sensitivity and accuracy of the monitoring logic.

### 4. Visual Observability & Dashboards
* Engineered a custom **CloudWatch Dashboard** to centralize infrastructure health metrics into a single "pane of glass."
* Deployed a **Line Widget** to visualize historical CPU trends, enabling faster identification of performance patterns and baseline deviations.

---
**Tech Stack:** AWS CloudWatch (Alarms, Dashboards, Metrics), Amazon SNS, Amazon EC2, Linux CLI (Stress testing tools).

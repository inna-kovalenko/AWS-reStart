# Infrastructure Monitoring and Compliance Management

---

## Lab Overview

I implemented a comprehensive monitoring and compliance strategy using **Amazon CloudWatch**, **AWS Systems Manager**, and **AWS Config**. This project focused on capturing system-level metrics, analyzing application logs in real-time, and automating infrastructure auditing to ensure operational reliability and organizational standards.

## Key Achievements & Technical Milestones

---

### 1. Hybrid Monitoring Agent Deployment

Overview of the task:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/48b49ff5-f6e1-4ea1-a004-8ce17aec71da" />

*   **Automated Installation**: Utilized **AWS Systems Manager Run Command** to deploy the CloudWatch agent across EC2 instances without manual login.

This shows how I selected certain configuration parameters when working with **Run Command**:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8e5bd83a-79b7-4058-8a37-96dc8adc6f69" />

*   **Centralized Configuration**: Engineered a JSON-based configuration file stored in **SSM Parameter Store** to standardize metric collection across the fleet.

The screenshot demonstrates how centralizing infrastructure monitoring was implemented by storing a JSON-based CloudWatch agent configuration to standardize log collection across EC2 instances: 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0f3aa549-cb19-4306-bd36-05e80fb90b23" />

*   **Deep Visibility**: Configured the agent to bridge the gap between standard hypervisor metrics and internal "in-guest" data, such as memory utilization and disk swap percentages.

### 2. Real-Time Log Analytics & Anomaly Detection
*   **Log Ingestion**: Successfully streamed Apache web server access and error logs to **CloudWatch Logs** for centralized analysis.
*   **Metric Filter Engineering**: Developed custom filter patterns `[ip, id, user, timestamp, request, status_code=404, size]` to isolate specific HTTP failure codes.
*   **Automated Alerting**: Established a **CloudWatch Alarm** integrated with **Amazon SNS** to trigger email notifications when error thresholds (e.g., five 404 errors per minute) were exceeded.

### 3. Event-Driven Automation
*   **State-Change Intelligence**: Created **CloudWatch Event Rules** to monitor EC2 lifecycle transitions in near-real-time.
*   **Instant Notifications**: Configured an automated response system that triggers SNS alerts immediately upon instance stoppage or termination, enabling rapid incident response.

### 4. Infrastructure Compliance Auditing
*   **Automated Governance**: Activated **AWS Config** to continuously record resource configurations and evaluate them against organizational benchmarks.
*   **Managed Rule Implementation**:
    *   **Tagging Compliance**: Enforced `required-tags` logic to ensure all resources contained a mandatory `project` key.
    *   **Cost Optimization**: Implemented `ec2-volume-inuse-check` to identify unattached EBS volumes, reducing "zombie" infrastructure costs.
*   **Drift Detection**: Analyzed compliance dashboards to distinguish between compliant and non-compliant assets across the AWS account.

---

## Technical Skills Demonstrated
*   **Observability**: Amazon CloudWatch (Metrics, Logs, Alarms, Events).
*   **Governance & Compliance**: AWS Config, Managed Rules, Resource Auditing.
*   **Management & Governance**: AWS Systems Manager (Run Command, Parameter Store).
*   **Messaging**: Amazon Simple Notification Service (SNS).
*   **Infrastructure Ops**: EC2 Monitoring, Log Aggregation, JSON Configuration.

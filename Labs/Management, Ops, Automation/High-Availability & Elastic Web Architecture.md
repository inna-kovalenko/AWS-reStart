# High-Availability & Elastic Web Architecture: Auto Scaling & Load Balancing 

**Primary Domain:** Ops & Management
**Key Concepts:** Infrastructure Automation & Scalability

## Lab Overview
I designed and deployed a fault-tolerant, elastic web architecture utilizing **Application Load Balancing (ALB)** and **EC2 Auto Scaling**. This project demonstrates the ability to automate infrastructure responses to fluctuating traffic patterns while maintaining high availability across multiple Availability Zones.

## Key Achievements & Technical Milestones

### 1. Golden Image & Template Strategy
* **AMI Engineering:** Created a "Golden Image" (Amazon Machine Image) from a pre-configured web server to ensure consistent deployments across the scaling group.
* **Launch Template Orchestration:** Defined a **Launch Template** specifying the instance class (t3.micro), security groups, and the custom AMI to standardize the production environment.

### 2. High-Availability Networking
* **Elastic Load Balancing (ELB):** Provisioned an **Application Load Balancer (ALB)** across two public subnets. Configured a **Target Group** with automated health checks to ensure traffic is only routed to "Healthy" instances.
* **Private Tier Security:** Directed the Auto Scaling group to launch instances within **Private Subnets**, ensuring that the backend application servers are never directly exposed to the public internet.

### 3. Elasticity & Monitoring (The "Self-Healing" Layer)
* **Dynamic Scaling Policies:** Implemented a **Target Tracking Scaling Policy** aimed at maintaining 50% CPU utilization.
* **CloudWatch Integration:** Utilized **Amazon CloudWatch Alarms** to monitor infrastructure performance. 
* **Load Stress Testing:** Successfully triggered a "Scale-Out" event by simulating high CPU demand, verifying that the Auto Scaling group increased capacity from 2 to 4 instances automatically.
* **Redundancy Validation:** Terminated the original source instance to prove the architecture’s independence from its initial components.

---

### TECH STACK & COMPONENTS
* **Compute:** Amazon EC2 (t3.micro), Custom AMI (Golden Image)
* **Networking:** Application Load Balancer (ALB), Lab VPC, Public/Private Subnets
* **Management:** Auto Scaling Groups (ASG), Launch Templates
* **Monitoring:** CloudWatch Alarms, Target Tracking Scaling Policies
* **Security:** Security Groups, Multi-tier Architecture (Private App Layer)

### CORE MILESTONES SUMMARY
* **Self-Healing Automation:** Configured a system to automatically scale capacity (2 to 4 instances) based on real-time CPU demand.
* **Fault Tolerance:** Deployed resources across multiple Availability Zones to ensure continuity during localized hardware failures.
* **Security Hardening:** Isolated the application tier within private subnets, using the ALB as the secure public-facing entry point.
* **Operational Monitoring:** Established a feedback loop using CloudWatch Alarms to align resource provisioning with actual workload.

### BUSINESS IMPACT
By implementing automated scaling and load balancing, I optimized infrastructure costs by ensuring pay-as-you-go efficiency while maintaining 100% application availability for end-users.

---
**Tech Stack:** AWS EC2, Application Load Balancer (ALB), Auto Scaling Groups (ASG), CloudWatch, VPC (Public/Private Subnets), AMI.

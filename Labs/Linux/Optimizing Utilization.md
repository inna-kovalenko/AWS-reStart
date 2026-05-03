# Optimizing Utilization

This lab focused on cost optimization and resource rightsizing. It demonstrated how to improve the efficiency of a cloud-based web application by removing redundant components and downsizing infrastructure to match actual demand.

---

## Lab Objectives
During this activity, the following competencies were developed:
*   **Optimized Amazon EC2 instances** to reduce monthly service costs.
*   **Utilized the AWS Pricing Calculator** to generate comparative cost estimates for cloud topologies.
*   **Managed software dependencies** by uninstalling decommissioned database services from production instances.
*   **Executed instance attribute modifications** using the AWS CLI to change instance types.

---

## Technical Scenario
The activity focused on the Café web application which had recently migrated its data to Amazon RDS. This migration left the original EC2 instance over-provisioned with a dormant local database and excessive CPU/RAM capacity.

### Optimization Strategy
| Action | Technical Detail | Business Value |
| :--- | :--- | :--- |
| **Software Cleanup** | Uninstalled MariaDB server and stopped the service. | Reduced storage (EBS) requirements and CPU overhead. |
| **Rightsizing** | Changed instance type from `t3.small` to `t3.micro`. | Lowered hourly compute costs while maintaining performance. |
| **Storage Reduction** | Reduced EBS volume requirement from 40 GB to 20 GB. | Minimized monthly storage fees. |

<img width="1364" height="718" alt="image" src="https://github.com/user-attachments/assets/694d7804-cf88-4b76-8189-f9d3f11d550d" />


---

## Task Summary

### 1. Instance Optimization via CLI
The optimization was performed using the AWS CLI through a dedicated CLI Host.
*   **Database Decommissioning**: Stopped the `mariadb` service and removed the server package using `yum` to free up system resources.
*   **Instance Modification**: Stopped the Café instance and utilized `modify-instance-attribute` to switch the instance type to `t3.micro`.
*   **Verification**: Restarted the instance and verified the new Public DNS and IP address to ensure the website remained functional.

### 2. Cost Estimation and Analysis
The AWS Pricing Calculator was used to model the financial impact of these changes.
*   **Baseline Estimate**: Calculated the "Before Optimization" cost (approx. $35.60/month) including the `t3.small` instance and 40 GB of storage.
*   **Optimized Estimate**: Generated an "After Optimization" model (approx. $25.18/month) reflecting the smaller instance and reduced storage.
*   **Savings Reporting**: Identified a projected monthly cost saving of approximately $10.42 (nearly 30% reduction).

---

## Infrastructure Requirements
*   **Connectivity**: Required SSH access to both the Café Instance and a CLI Host instance.
*   **CLI Configuration**: Applied AWS credentials (Access Key/Secret Key) and region settings to enable remote management.
*   **Wait States**: Monitored EC2 state transitions to ensure instances reached the `running` status before verification.

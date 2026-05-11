# Elastic Web Architecture: CLI-Driven Scaling & Load Balancing

**Domain:** Compute / Management & Governance


**Key Concepts:** Infrastructure Automation, High Availability, Target Tracking Scaling

---

### ARCHITECTURAL FLOW
Implemented a highly available, self-healing web architecture by transitioning from a single manual EC2 instance to an automated **Auto Scaling Group (ASG)**. The final state utilizes an **Application Load Balancer (ALB)** to distribute traffic across private subnets in multiple Availability Zones, ensuring regional resilience and fault tolerance.


### TECHNICAL EXECUTION

#### 1. Image Lifecycle & CLI Automation
* **Standardized Provisioning:** Leveraged the **AWS CLI** to bootstrap a baseline EC2 instance with a custom PHP stress-test application via User Data scripts.

This demonstrates the Instance was successfully launched & assigned a Public DNS Name:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/89a5ca5f-d241-4145-b29e-1b90352af8ba" />

* **Custom AMI Creation:** Engineered a golden image (**AMI**) from the configured instance to serve as the immutable blueprint for all fleet expansions, ensuring environment parity across the cluster.

This shows a new AMI being created based on this instance:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a373afb7-dc43-40aa-bab8-d38beeb54ad8" />


#### 2. Load Balancing & Traffic Management
* **ALB Deployment:** Provisioned an **Application Load Balancer** across two Public Subnets to act as the single point of entry for end-users, decoupling the frontend from backend instances.
* **Target Group Logic:** Defined health check parameters targeting `index.php` to ensure the balancer only routes traffic to "Healthy" instances, automatically bypassing failed nodes.

Confirmation of completion of the steps above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1989a9d8-2bf8-4cf2-9045-c94ebd82dc60" />

#### 3. Scaling Strategy & Launch Templates
* **Launch Template Versioning:** Defined instance specifications (including AMI ID, instance type (`t3.micro`), and Security Group associations) within a version-controlled **Launch Template**.

This demonstrates I finalized a standardized launch template to define the AMI, instance type, security group parameters, ensuring consistent and repeatable deployments across the Auto Scaling Group:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e117e66d-c092-46ad-b6a5-d0aada724b6b" />


* **Auto Scaling Group (ASG) Configuration:** Established an ASG spanning multiple **Private Subnets** to protect application logic from direct internet exposure.
* **Elasticity Logic:** Implemented a **Target Tracking Scaling Policy** aimed at maintaining an average **CPU Utilization of 50%**, allowing the infrastructure to dynamically scale out to 4 instances or scale in to 2 based on real-time demand.

#### 4. Stress Testing & Performance Validation
* **Load Simulation:** Triggered a high CPU load on the fleet to simulate a production traffic spike.
* **Automated Recovery:** Monitored the **CloudWatch-triggered** alarm response, confirming the ASG successfully provisioned additional capacity to normalize CPU metrics and maintain application performance.

---

### TECH STACK & COMPONENTS
* **Compute:** Amazon EC2, Auto Scaling Groups (ASG)
* **Image Management:** Amazon Machine Images (AMI)
* **Networking:** Application Load Balancer (ALB), Target Groups, VPC (Public/Private Subnets)
* **Management:** AWS CLI, Launch Templates, CloudWatch Metrics
* **Security:** Security Groups (Stateful Inspection), Private Subnet Isolation

### OPERATIONAL VALUE
This implementation demonstrates the shift from manual resource management to **automated, elastic infrastructure**. By utilizing ALBs and target-tracking policies, the architecture achieves a balance of **High Availability** and **Cost Optimization**, ensuring resources are consumed only when necessary while maintaining a seamless user experience.

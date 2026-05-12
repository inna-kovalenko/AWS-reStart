# PROJECT: Infrastructure Automation via AWS CloudFormation
**Domain:** Management & Governance / DevOps  
**Key Concepts:** Infrastructure as Code (IaC), Template Versioning, Automated Provisioning

---

### ARCHITECTURAL SYNOPSIS
Transitioned from manual resource configuration to **Infrastructure as Code (IaC)** by defining a standardized environment within **CloudFormation** templates. This approach ensured consistent, repeatable deployments of a virtual network, storage, and compute resources while eliminating human error during provisioning.



### ACHIEVEMENTS

#### 1. Automated Stack Deployment
* Deployed an initial **CloudFormation stack** containing a custom **VPC** and **Security Group**.
* Utilized **YAML**-formatted templates to define infrastructure parameters, resources, and outputs.
* Monitored real-time stack events to verify the optimal creation order of dependent networking components.

#### 2. Iterative Template Configuration
* Updated the existing template to include an **Amazon S3** bucket.
* Executed stack updates by uploading revised templates, allowing CloudFormation to calculate and apply only the necessary changes via **Change Sets**.

#### 3. Dynamic Resource Integration
* Implemented a specialized parameter to fetch the latest **Amazon Linux 2 AMI ID** directly from the **AWS Systems Manager Parameter Store**.
* Integrated an **Amazon EC2** instance into the stack by using the `!Ref` keyword to link it to previously defined subnets and security groups.
* Applied standardized resource tags to ensure organizational visibility and tracking within the console.

#### 4. Automated Lifecycle Management
* Validated the efficiency of IaC by executing a single **Delete stack** command to terminate the entire environment.
* Confirmed that CloudFormation automatically and cleanly removed the S3 bucket, EC2 instance, and VPC resources in the correct sequence.

---

### TECH STACK AND COMPONENTS
* **Orchestration:** AWS CloudFormation (YAML)
* **Compute:** Amazon EC2 (t3.micro)
* **Storage:** Amazon S3
* **Networking:** Amazon VPC, Security Groups
* **Configuration Management:** AWS Systems Manager Parameter Store

### OPERATIONAL VALUE
This project established a foundation for **DevOps automation** by treating infrastructure as a version-controlled asset. The resulting workflow reduced deployment times and ensured that complex environments remained identical across different regions and accounts.

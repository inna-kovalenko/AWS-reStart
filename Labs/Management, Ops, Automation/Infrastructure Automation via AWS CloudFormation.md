# Infrastructure Automation via AWS CloudFormation

**Domain:** Management & Governance / DevOps  
**Key Concepts:** Infrastructure as Code (IaC), Template Versioning, Automated Provisioning

---

### ARCHITECTURAL SYNOPSIS
Transitioned from manual resource configuration to **Infrastructure as Code (IaC)** by defining a standardized environment within **CloudFormation** templates. This approach ensured consistent, repeatable deployments of a virtual network, storage, and compute resources while eliminating human error during provisioning.

This gives overview of the task with an example of how key elements appear in the template written in **YAML** format:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7ef2d291-400b-48a1-b8bf-2dc34915560c" />


### ACHIEVEMENTS

#### 1. Automated Stack Deployment
* Deployed an initial **CloudFormation stack** containing a custom **VPC** and **Security Group**.
* Utilized **YAML**-formatted templates to define infrastructure parameters, resources, and outputs.
* Monitored real-time stack events to verify the optimal creation order of dependent networking components.

This shows I utilized the CloudFormation Timeline view to observe the real-time orchestration and dependency-ordered creation of VPC infrastructure components as they transitioned to a complete state:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d1950b01-b892-44c5-8cf8-8d6c681a2580" />

#### 2. Iterative Template Configuration
* Updated the existing template to include an **Amazon S3** bucket.

Here how the update looked like:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4e9d8518-b7f0-4839-8afa-e14f16081ddf" />

* Executed stack updates by uploading revised templates, allowing CloudFormation to calculate and apply only the necessary changes via **Change Sets**.

This shows only S3 bucket would be added by **CloudFormation**
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5d0d8c53-35d4-4805-a252-ff07efccce88" />

This demonstrates the template was updated successfully:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2db1bd09-0831-4795-8504-dd1a69aee1ca" />

#### 3. Dynamic Resource Integration
* Implemented a specialized parameter to fetch the latest **Amazon Linux 2 AMI ID** directly from the **AWS Systems Manager Parameter Store**.
* Integrated an **Amazon EC2** instance into the stack by using the `!Ref` keyword to link it to previously defined subnets and security groups.
* Applied standardized resource tags to ensure organizational visibility and tracking within the console.

This documents work on the steps above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cc4036b2-22ec-42e4-b3b2-01b0771ec0a6" />

The screenshot shows verification stage - checking how adding a Web Server was done:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a54c9e61-6ba4-474e-bb32-e4c4a6278bd4" />

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

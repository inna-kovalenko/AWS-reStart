# Next-Generation 3D E-Commerce Architecture

> Designed a highly available, scalable AWS cloud architecture to deliver heavy 3D assets globally with low latency, strong security, and cost optimization.

---

## 1. Executive Summary

This project presents a **cloud-native, highly available architecture** for a global 3D e-commerce platform.

The main challenge is delivering **heavy 3D assets (e.g. furniture, gadgets)** to millions of users without performance issues.

To address this, the architecture combines:
- Amazon CloudFront for global content delivery  
- Amazon S3 for durable asset storage  
- Amazon Aurora for high-performance data processing  

The system is designed to be **secure, scalable, and easy to understand**, with clearly structured networking layers and standardized service representation.

---

## 2. Architecture Overview

The architecture is organized into clearly defined layers and boundaries to improve readability and reflect real-world AWS design standards.

### Core Services and Roles

| Service | Purpose | Why it was chosen |
|--------|--------|------------------|
| Route 53 | DNS Management | Routes users to the fastest endpoint using latency-based routing |
| AWS IAM | Access Control | Enforces secure, role-based access (least privilege) |
| AWS WAF | Security | Filters malicious traffic at the edge |
| CloudFront | CDN | Caches 3D assets close to users |
| Amazon S3 | Storage | Durable storage for large 3D files |
| ELB (ALB) | Load Balancing (Application LB) | Distributes traffic across compute resources |
| EC2 (Auto Scaling) | Compute | Dynamically scales backend capacity |
| AWS Lambda | Serverless | Handles event-driven background tasks |
| Amazon Aurora | Relational DB | High availability and failover support |
| DynamoDB | NoSQL DB | Fast product catalog access |
| VPC Endpoints | Private Access | Enables secure internal data transfer (bypassing public internet) |

---

## 3. Architecture Design Principles

### Clear Structure and Boundaries
- The architecture is deployed inside a **VPC with multiple Availability Zones**
- **Public and Private subnets** are clearly separated
- Compute and databases are placed in **private subnets**, not exposed to the internet
- External access is controlled through defined entry points

### Secure Internal Communication
- Internal traffic uses **VPC Endpoints** to connect to S3 and DynamoDB
- This keeps data transfers inside the AWS network
- Avoids unnecessary exposure to the public internet

### Standardized and Readable Design
- Services are clearly labeled with their **respective AWS serices logos**
- Components are grouped by function (Compute, Database, Networking)
- The layout follows a **simple top-down flow**, making it easy to explain and present

  <img width="762" height="771" alt="AWS Project Architecture-Diagram-Final1-12 4 drawio" src="https://github.com/user-attachments/assets/a876fd1f-02dd-476e-ac2f-bb3b3fce4080" />

---

## 4. Key Architecture Benefits

### High Availability
- Multi-AZ deployment ensures resilience
- Automatic failover with ALB and Route 53
- Aurora provides database redundancy

### Scalability
- Auto Scaling Group adjusts EC2 capacity dynamically
- DynamoDB and Lambda scale automatically

### Performance
- CloudFront reduces latency with edge caching
- Private data paths improve speed and efficiency

### Security
- Private subnet architecture protects backend resources
- IAM enforces least privilege access
- AWS WAF filters malicious requests before they reach the system

### Cost Optimization
- Monitoring tools (CloudWatch, Trusted Advisor) identify inefficiencies
- Lambda reduces always-on infrastructure costs
- S3 Intelligent-Tiering optimizes storage expenses
- VPC Endpoints reduce data transfer costs

---

## 5. Networking & Traffic Flow

1. User request → Route 53  
2. Route 53 → + WAF + CloudFront  
3. CloudFront + WAF → request inspection  
4. Request enters VPC via Internet Gateway  
5. ELB (ALB) routes traffic to EC2 (private subnet)  
6. EC2 retrieves:
   - Product data → DynamoDB  
   - User/order data → Aurora  
7. 3D assets delivered from S3 via VPC Endpoint  

---

## 6. Design Trade-offs & Challenges

- **Aurora vs RDS**  
  Higher cost but avoids a single point of failure  

- **Multiple Databases**  
  Adds complexity but improves performance and scalability  

- **Multi-AZ Setup**  
  More complex but critical for high availability  

- **CloudFront Costs**  
  Managed through caching and storage optimization  

---

## Summary

This architecture demonstrates how to design a **production-ready cloud system** that balances:

- Performance  
- Scalability  
- Security  
- Cost efficiency  

It reflects real-world cloud engineering practices and is structured for both **technical understanding and clear communication** during presentations and reviews.

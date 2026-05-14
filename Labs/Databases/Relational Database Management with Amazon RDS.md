# Relational Database Management with Amazon RDS

## Executive Summary
This lab focused on deploying and managing an AWS-managed relational database environment. By leveraging Amazon RDS, I successfully provisioned a scalable database instance, performed schema design (DDL), and executed complex data manipulation (DML) to solve business-related data needs.

## Key Technical Achievements
*   **RDS Instance Provisioning**: Launched and configured a high-performance Amazon RDS DB instance (MySQL) within a custom Lab VPC.

Here it is visible I selected **MySQL**, **Free-Tier** option, in a single AZ:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/15478b89-9408-4739-a10c-90d92a9a1a85" />

This scresnshot demonstrates I configured **VPC**, **DB Subnet**, **Firewall** & banned **Public Access** (such configuration of **Security Groups** and private networking was needed to ensure the database would be only accessible via a secure Linux jump host):
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/dba659f5-f916-4fb0-a2ad-0b753e54320f" />


*   **Security & Connectivity**: Established secure SSH tunneling via a Linux jump host and configured Security Groups to permit controlled MySQL client access.

This shows connection was successfully established and the database (`challengelabdb`) had also been created:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/02bee699-28bb-4437-aae2-24fc03857719" />

Here I installed the **MariaDB** client on the **Amazon Linux jump host** to enable secure CLI-based communication with the RDS instance:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e4420e19-d189-41e2-8a6b-4998d8970c87" />

Then, I identified the unique **RDS Endpoint** to establish a direct network connection between the EC2 client and the database engine:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b67184ae-0f2f-4fdc-b54f-9ba4b6ec7146" />

*   **Schema Design (DDL)**: Engineered normalized tables (`RESTART` and `CLOUD_PRACTITIONER`) with constrained data types including Integers, Varchars, and DateTimes.
*   **Data Ingestion (DML)**: Populated schemas with sample datasets using multi-record insertion scripts to simulate real-world data environments.
*   **Relational Querying**: Performed advanced SQL operations, including **Inner Joins**, to aggregate data across multiple tables for integrated reporting.

## Tools & Technologies
*   **AWS Services**: Amazon RDS (Aurora/MySQL), Amazon EC2, Amazon VPC.
*   **Database Tools**: MySQL Client, SQL (DDL/DML).
*   **Security**: SSH, PEM/PPK Authentication, Security Groups.

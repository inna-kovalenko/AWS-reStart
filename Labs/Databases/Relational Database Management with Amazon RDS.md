# Relational Database Management with Amazon RDS

## Executive Summary
This lab focused on deploying and managing an AWS-managed relational database environment. By leveraging Amazon RDS, I successfully provisioned a scalable database instance, performed schema design (DDL), and executed complex data manipulation (DML) to solve business-related data needs.

## Key Technical Achievements
*   **RDS Instance Provisioning**: Launched and configured a high-performance Amazon RDS DB instance (Amazon Aurora/MySQL) within a custom Lab VPC.
*   **Security & Connectivity**: Established secure SSH tunneling via a Linux jump host and configured Security Groups to permit controlled MySQL client access.
*   **Schema Design (DDL)**: Engineered normalized tables (`RESTART` and `CLOUD_PRACTITIONER`) with constrained data types including Integers, Varchars, and DateTimes.
*   **Data Ingestion (DML)**: Populated schemas with sample datasets using multi-record insertion scripts to simulate real-world data environments.
*   **Relational Querying**: Performed advanced SQL operations, including **Inner Joins**, to aggregate data across multiple tables for integrated reporting.

## Tools & Technologies
*   **AWS Services**: Amazon RDS (Aurora/MySQL), Amazon EC2, Amazon VPC.
*   **Database Tools**: MySQL Client, SQL (DDL/DML).
*   **Security**: SSH, PEM/PPK Authentication, Security Groups.

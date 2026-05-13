# Relational Database Table Operations

---

## Lab Overview

I performed fundamental database administration and table operations on a relational `world` database hosted on an AWS EC2 Command Host. This project focused on the complete data lifecycle, from initial environment configuration to schema modification and resource decommissioning using industry-standard SQL.

Visualization of the task:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2489ab51-3215-4944-bc32-9d37d5f544f7" />

## Key Achievements & Technical Milestones

---

### 1. Database Connectivity & Environment Management
*   **Established** a secure terminal session to a Linux-based Command Host using **AWS Systems Manager (SSM) Session Manager**.
*   **Managed** authenticated administrative access to a **MySQL** database engine using CLI-based credential management.
*   **Configured** the local environment by elevating privileges to `sudo su` and navigating to the root application directory.

### 2. Schema Architecture & Data Initialization
*   **Engineered** a new relational database named `world` to serve as the primary data container.

This demonstrates completion of the steps above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/552bd973-9c1b-4f2c-b90c-935e8e469e3a" />

*   **Defined** complex table structures using the `CREATE TABLE` statement, implementing specific constraints for data integrity.
*   **Implemented** primary keys and data types (CHAR, INT, ENUM) to ensure the `country` table followed a strict schema.

### 3. Structural Auditing & Table Modification
*   **Performed** schema exploration using `SHOW COLUMNS` to audit existing table structures and identify naming inconsistencies.

This shows completion of the previous steps up to the point where a spelling error was found:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e8e9a4bf-efaf-44e9-8f24-5396f8b0bc46" />

*   **Executed** structural changes using the `ALTER TABLE` command to rename columns and correct typographical errors without data loss.
*   **Validated** schema updates in real-time to ensure the database accurately reflected the intended business logic.

### 4. Resource Lifecycle & Decommissioning
*   **Managed** the safe removal of relational assets using the `DROP TABLE` command for specific tables (`city`, `country`).
*   **Decommissioned** the entire `world` database environment to maintain high cloud hygiene and reduce resource overhead.
*   **Verified** successful cleanup using `SHOW DATABASES` to ensure no orphaned resources remained on the instance.

---

## Technical Skills Demonstrated
*   **Cloud Infrastructure:** Amazon EC2, AWS Systems Manager.
*   **Database Administration:** MySQL, Relational Schema Design.
*   **SQL Proficiency:** DDL (Data Definition Language) - `CREATE`, `ALTER`, `DROP`, `SHOW`.
*   **Systems Operation:** Linux CLI, Root User Management, Directory Navigation.

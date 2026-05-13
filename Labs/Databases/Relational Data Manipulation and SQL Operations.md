# Relational Data Manipulation and SQL Operations

---

## Lab Overview

I performed advanced data manipulation on a relational `world` database hosted on an AWS EC2 Command Host[cite: 1]. This project focused on the core DML (Data Manipulation Language) lifecycle—including inserting, updating, deleting, and bulk-importing datasets—to validate database configurations and maintain data integrity[cite: 1].

## Key Achievements & Technical Milestones

---

### 1. Database Connectivity & Environment Management
*   **Established** a secure terminal session to a Linux-based Command Host using **AWS Systems Manager (SSM) Session Manager**[cite: 1].
*   **Managed** authenticated administrative access to a **MySQL** database engine using CLI-based credential management[cite: 1].
*   **Performed** initial schema exploration using `SHOW DATABASES` to audit the available data environment[cite: 1].

### 2. Record Creation & Data Insertion
*   **Engineered** new data records within the `country` table using the `INSERT INTO` statement[cite: 1].
*   **Applied** strict schema adherence by aligning input values (such as Country Codes, Population, and IndepYear) with the predefined table structure[cite: 1].
*   **Validated** successful data entry by executing targeted `SELECT` queries to confirm record presence[cite: 1].

### 3. Structural Updates & Data Modification
*   **Executed** global data updates using the `UPDATE` statement to modify existing records in bulk[cite: 1].
*   **Refined** specific attributes such as `Population` and `SurfaceArea` across multiple rows simultaneously[cite: 1].
*   **Analyzed** the behavior of DML statements when executed without a `WHERE` clause, demonstrating high-impact global updates[cite: 1].

### 4. Data Deletion & Bulk Import Operations
*   **Performed** secure data removal using the `DELETE` statement, including the temporary suspension of `FOREIGN_KEY_CHECKS` to ensure referential integrity during cleanup[cite: 1].
*   **Automated** large-scale data loading by importing an external `.sql` backup file via the Linux command line[cite: 1].
*   **Verified** the restoration of multi-table environments (`city`, `country`, `countrylanguage`) to ensure the database was fully operational after the bulk import[cite: 1].

---

## Technical Skills Demonstrated
*   **Cloud Infrastructure:** Amazon EC2, AWS Systems Manager[cite: 1].
*   **Database Management:** MySQL, Data Manipulation Language (DML)[cite: 1].
*   **SQL Proficiency:** `INSERT`, `UPDATE`, `DELETE`, `SELECT`, `SET FOREIGN_KEY_CHECKS`[cite: 1].
*   **Systems Operation:** Linux CLI, SQL Script Importing, Root User Management[cite: 1].

# Relational Data Manipulation and SQL Operations

---

## Lab Overview

I performed advanced data manipulation on a relational `world` database hosted on an AWS EC2 Command Host. This project focused on the core DML (Data Manipulation Language) lifecycle, including inserting, updating, deleting, and bulk-importing datasets to validate database configurations and maintain data integrity.

## Key Achievements & Technical Milestones

---

### 1. Database Connectivity & Environment Management
*   **Established** a secure terminal session to a Linux-based Command Host using **AWS Systems Manager (SSM) Session Manager**.
*   **Managed** authenticated administrative access to a **MySQL** database engine using CLI-based credential management.
*   **Performed** initial schema exploration using `SHOW DATABASES` to audit the available data environment.

### 2. Record Creation & Data Insertion
*   **Engineered** new data records within the `country` table using the `INSERT INTO` statement.
*   **Applied** strict schema adherence by aligning input values like Country Codes, Population, and IndepYear with the predefined table structure.
*   **Validated** successful data entry by executing targeted `SELECT` queries to confirm record presence.

### 3. Structural Updates & Data Modification
*   **Executed** global data updates using the `UPDATE` statement to modify existing records in bulk.
*   **Refined** specific attributes such as `Population` and `SurfaceArea` across multiple rows simultaneously.
*   **Analyzed** the behavior of DML statements when executed without a `WHERE` clause, demonstrating high-impact global updates.

### 4. Data Deletion & Bulk Import Operations
*   **Performed** secure data removal using the `DELETE` statement, including the temporary suspension of `FOREIGN_KEY_CHECKS` to ensure referential integrity during cleanup.
*   **Automated** large-scale data loading by importing an external `.sql` backup file via the Linux command line.
*   **Verified** the restoration of multi-table environments (`city`, `country`, `countrylanguage`) to ensure the database was fully operational after the bulk import.

---

## Technical Skills Demonstrated
*   **Cloud Infrastructure:** Amazon EC2, AWS Systems Manager.
*   **Database Management:** MySQL, Data Manipulation Language (DML).
*   **SQL Proficiency:** `INSERT`, `UPDATE`, `DELETE`, `SELECT`, `SET FOREIGN_KEY_CHECKS`.
*   **Systems Operation:** Linux CLI, SQL Script Importing, Root User Management.

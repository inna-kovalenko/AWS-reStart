# Relational Data Analysis and SQL Function Engineering

---

## Lab Overview

I performed advanced data manipulation and analysis on a relational `world` database hosted on an AWS EC2 Command Host. This project focused on utilizing SQL functions to extract business intelligence, perform data auditing, and generate aggregate statistics from complex datasets.

Visualization of the task:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/256fbdc6-a566-41f8-8ae6-3559efcfdc7f" />


## Key Achievements & Technical Milestones

---

### 1. Database Connectivity & Environment Management
*   **Established** a secure terminal session to a Linux-based Command Host using **AWS Systems Manager (SSM) Session Manager**.
*   **Managed** authenticated administrative access to a **MySQL** database engine using CLI-based credential management.
*   **Performed** initial schema exploration using `SHOW DATABASES` and `SHOW COLUMNS` to audit table structures and data types.

### 2. Aggregate Data Analysis & Auditing
*   **Utilized** the `COUNT()` function to perform quantitative analysis on the dataset, identifying the total volume of records within the `country` table.

An example of output after performing the tasks above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9854c05c-5164-4624-a113-1d4c7c2f6ad2" />

*   **Extracted** targeted intelligence by querying specific columns such as Name, Capital, and Population to streamline data visibility.
*   **Applied** the `AS` keyword to generate user-friendly aliases for technical column names, improving the readability of business reports.

### 3. Data Sorting & Result Set Optimization
*   **Implemented** complex sorting logic using the `ORDER BY` statement to organize result sets by specific metrics.
*   **Managed** data hierarchy by applying `DESC` (descending) operators to prioritize high-value records, such as ranking nations by population density.
*   **Optimized** the analytical workflow by creating ordered result sets that are easier for stakeholders to view and interpret.

### 4. Advanced Logical Filtering & Operators
*   **Engineered** precision queries using the `WHERE` clause to isolate records meeting specific business criteria.
*   **Applied** comparison operators (`>`, `<`, `=`) to filter data based on numerical thresholds, such as identifying regions with populations exceeding 50 million.
*   **Constructed** multi-conditional queries using the `AND` operator to find specific intersections of data, such as identifying high-population countries within Southern Europe.

---

## Technical Skills Demonstrated
*   **Cloud Infrastructure:** Amazon EC2, AWS Systems Manager.
*   **Database Management:** MySQL, Relational Data Auditing.
*   **SQL Proficiency:** `SELECT`, `COUNT()`, `WHERE`, `ORDER BY`, `AS`, Logical Operators (`AND`, `>`, `<`, `=`).
*   **Systems Operation:** Linux CLI, Root User Management, Directory Navigation.

# Relational Data Analysis and SQL Function Engineering

## Lab Overview
I performed advanced data manipulation and analysis on a relational `world` database hosted on an AWS EC2 Command Host. This project focused on utilizing SQL functions to extract business intelligence, perform string manipulation, and generate aggregate statistics from complex datasets.

This is a visual breakdown of task:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bcb8ebab-00e4-4e90-9812-faaef7973c9f" />


## Key Achievements & Technical Milestones

### 1. Database Connectivity & Environment Management
* Established a secure terminal session to a Linux-based **Command Host** using **AWS Systems Manager (SSM) Session Manager**.
* Managed authenticated administrative access to a **MySQL** database engine using CLI-based credential management.
* Performed schema exploration using `SHOW DATABASES` and `SELECT *` to audit table structures (`city`, `country`, `countrylanguage`).

This documents steps above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/353c5f40-fcd6-45c5-9652-05533d22940b" />



### 2. Aggregate Data Analytics
* Synthesized large-scale population data using aggregate functions including **SUM()**, **MIN()**, **MAX()**, and **AVG()**.
* Calculated dataset metadata using the **COUNT()** function to verify record integrity across 239 countries.
* Generated summary reports to identify global population extremes and averages without manual data processing.

Use of the functions above:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b766093d-1698-44ed-9372-9b2e0ba5e1a9" />

### 3. Advanced String Manipulation & Data Cleaning
* Engineered complex queries using **SUBSTRING_INDEX()** to parse and split geographic region strings into distinct data columns.
* Applied **TRIM()** and **LENGTH()** functions within `WHERE` clauses to filter records based on specific character-count criteria.

This demonstrates working with the above functions:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e2a131dc-a619-42ba-8d2f-0a81d8b386e6" />

* Utilized **DISTINCT()** to eliminate redundant records and ensure high-fidelity reporting of unique geographical regions.

This shows completion of the step above & the challenge below:
<img width="925" height="496" alt="image" src="https://github.com/user-attachments/assets/14b7dec5-ecef-48fc-b93e-5e626af4935a" />


### 4. Logic & Query Optimization (Challenge Task)
* Solved a complex data-splitting requirement by nesting string functions to separate "Micronesia/Caribbean" into two distinct aliases: `Region Name 1` and `Region Name 2`.
* Applied logical filtering using the `WHERE` clause to isolate specific regional subsets for targeted reporting.

---
**Tech Stack:** SQL (MySQL/MariaDB), AWS EC2, SSM Session Manager, Relational Database Management (RDBMS).

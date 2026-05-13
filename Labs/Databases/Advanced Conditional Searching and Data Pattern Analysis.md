# Advanced Conditional Searching and Data Pattern Analysis

---

## Lab Overview

I executed complex data retrieval operations on a relational `world` database hosted on an **AWS EC2 Command Host**. This project focused on engineering high-precision queries using conditional logic, pattern matching, and mathematical functions to extract specific insights from global datasets.

## Key Achievements & Technical Milestones

---

### 1. Database Connectivity & Security
*   **Established** an encrypted terminal session via **AWS Systems Manager (SSM) Session Manager** to a Linux-based Command Host.
*   **Managed** administrative database access using the **MySQL** command-line interface with secure credential authentication.
*   **Configured** the terminal environment to support advanced SQL queries and resource management.

### 2. Range-Based Data Filtering
*   **Optimized** search conditions using the `BETWEEN` operator to isolate records within specific numerical ranges, replacing less efficient logical combinations.
*   **Implemented** multi-conditional filtering using `WHERE` clauses and `AND` operators to define strict boundaries for population datasets (e.g., filtering for nations with 50M to 100M residents).
*   **Validated** query accuracy by comparing result sets across different logical implementations.

### 3. Pattern Matching & String Manipulation
*   **Applied** the `LIKE` operator combined with `%` wildcards to perform flexible string pattern matching across large text columns.
*   **Engineered** case-insensitive searches by nesting the `LOWER()` function within the `WHERE` clause, ensuring data retrieval was not limited by specific database collation settings.
*   **Isolated** regional data clusters, such as all entries containing "Europe" or "Central," to create targeted geographic reports.

### 4. Aggregate Functions & Business Intelligence
*   **Utilized** the `SUM()` function to calculate aggregate statistics, such as total continental population and combined surface area, directly from the database.
*   **Enhanced** reporting clarity by applying the `AS` keyword to create professional column aliases (e.g., "Europe Population Total").
*   **Calculated** specific metrics for North America as part of a technical challenge to demonstrate proficiency in multi-function query construction.

The output of completing the challenge above (also on top it is visible I utilized the `LOWER` function to perform a case-sensitive search):
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9643fc8b-9885-43e7-ae06-32d4b2cc4805" />


---

## Technical Skills Demonstrated
*   **Cloud Infrastructure:** Amazon EC2, AWS Systems Manager.
*   **Database Engineering:** MySQL, Relational Data Filtering.
*   **Advanced SQL Proficiency:** `SELECT`, `WHERE`, `BETWEEN`, `LIKE`, `SUM()`, `LOWER()`, `AS`.
*   **Logical Operations:** Wildcard searching (`%`), Range validation, Aggregate math.
*   **Systems Management:** Linux CLI, Root User Operations, Environment Configuration.

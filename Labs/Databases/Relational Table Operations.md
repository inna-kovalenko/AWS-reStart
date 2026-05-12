# Relational Table Operations

This lab focused on the lifecycle of a relational database, incl. management of schemas and tables via the MySQL command-line interface on a Linux-based AWS environment. 


I performed end-to-end operations from establishing secure connections to designing schemas to managing data integrity through structural changes to decommissioning resources.

---

### Technical Objectives
*   **Secure Access**: Established a remote connection to a Linux Command Host via AWS Systems Manager to run SQL queries against a relational engine.
*   **Schema Design**: Constructed a `world` database and defined a multi-attribute `country` table using SQL data types like CHAR, ENUM, and INT.
*   **Structural Refinement**: Applied `ALTER` statements to modify existing table structures and fix naming errors without impacting data integrity.
*   **Environment Decommissioning**: Executed precise `DROP` sequences to safely remove resources and verify successful deletion through CLI auditing.

---

### Implementation Steps

#### 1. Database Connectivity
To interface with the relational engine, I navigated the Linux environment and initiated the MySQL client using established credentials:

# Elevate privileges and navigate to the home directory
sudo su
cd /home/ec2-user/

# Access the MySQL shell using root credentials
mysql -u root --password='re:St@rt!9'

#### 2. Creating the Schema
I initialized the environment by creating a dedicated database and a robust table structure based on regional statistics.

-- Initialize the database container
CREATE DATABASE world;
USE world;

-- Define the country table with specific data constraints
CREATE TABLE country (
  `Code` CHAR(3) NOT NULL DEFAULT '',
  `Name` CHAR(52) NOT NULL DEFAULT '',
  `Continent` ENUM('Asia','Europe','North America','Africa','Oceania','Antarctica','South America') NOT NULL DEFAULT 'Asia',
  `Region` CHAR(26) NOT NULL DEFAULT '',
  `Population` INT(11) NOT NULL DEFAULT '0',
  PRIMARY KEY (`Code`)
);

#### 3. Handling Schema Drift & Modifications
During the audit phase, a misspelling was identified in the schema (`Conitinent`). I applied an `ALTER` statement to refine the structure efficiently without needing to rebuild the table.

-- Audit the current column properties
SHOW COLUMNS FROM world.country;

-- Rename the column to fix the spelling error
ALTER TABLE world.country RENAME COLUMN Conitinent TO Continent;

#### 4. Safe Resource Deletion (Cleanup)
To demonstrate governance and environment management, I performed a controlled teardown of the resources, confirming deletion at each stage.

-- Remove specific tables
DROP TABLE world.city;
DROP TABLE world.country;

-- Verify the removal of the database
DROP DATABASE world;
SHOW DATABASES;

---

### Key Skills Demonstrated
*   **Database Governance**: Managed the full lifecycle of relational resources including creation, auditing, and deletion.
*   **Operational Security**: Utilized AWS Systems Manager for secure CLI-based instance management and database interfacing.
*   **Data Integrity**: Implemented precise SQL Data Definition Language (DDL) to ensure schema accuracy and corrected structural drift.

# Relational Table Operations

This lab involved performing fundamental database and table operations using a MySQL client on an Amazon EC2 command host. I practiced the core lifecycle of data management, including creation, auditing, structural modification, and decommissioning.

---

### Key Achievements
*   **Established Database Connectivity**: Connected to a Linux-based Command Host and authenticated into the MySQL shell using root credentials.
*   **Defined Data Structures**: Created the `world` database and engineered the `country` table schema with specific data types including CHAR, ENUM, and FLOAT.
*   **Managed Schema Integrity**: Utilized the `ALTER` statement to rename columns and correct structural errors identified during audits.
*   **Executed Resource Decommissioning**: Performed controlled `DROP` operations to safely delete tables and databases after verifying task completion.

---

### Implementation Workflow

#### 1. Environment Access
I accessed the Command Host via Session Manager and initiated the MySQL client to interface with the relational database.

# Elevated privileges and accessed the database
sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'

#### 2. Database and Table Creation
I built the organizational structure for the data by creating a new database and defining a detailed table schema.

# Initialized the environment
CREATE DATABASE world;
USE world;

# Defined the table schema
CREATE TABLE world.country (
  `Code` CHAR(3) NOT NULL,
  `Name` CHAR(52) NOT NULL,
  `Continent` ENUM('Asia','Europe','North America','Africa','Oceania','Antarctica','South America') NOT NULL DEFAULT 'Asia',
  PRIMARY KEY (`Code`)
);

#### 3. Schema Audit and Modification
I used discovery commands to inspect the table structure and applied corrections to the schema configuration.

# Verified table columns
SHOW COLUMNS FROM world.country;

# Corrected column naming error
ALTER TABLE world.country RENAME COLUMN Conitinent TO Continent;

#### 4. Resource Cleanup
To conclude the operations, I successfully decommissioned the created resources to restore the environment to its original state.

# Deleted tables and the database
DROP TABLE world.city;
DROP TABLE world.country;
DROP DATABASE world;

# Final verification
SHOW DATABASES;

---

### Technical Skills
*   **SQL Fundamentals**: Proficient in CREATE, SHOW, ALTER, and DROP statements.
*   **Linux CLI**: Managed system directories and elevated user permissions.
*   **Data Governance**: Audited and modified database schemas to ensure accuracy.

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

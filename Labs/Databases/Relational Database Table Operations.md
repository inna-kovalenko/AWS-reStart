# Relational Database Table Operations

This lab involved performing fundamental database and table operations using a MySQL client on an Amazon EC2 command host. I practiced the core lifecycle of data management, including creation, auditing, structural modification, and decommissioning.

## Technical Tasks Completed

### 1. Established Secure Connection
I connected to a Linux Command Host via AWS Systems Manager and accessed the MySQL shell.

- Command to switch to root: sudo su
- Command to navigate home: cd /home/ec2-user/
- Command to log into MySQL: mysql -u root --password='re:St@rt!9'

### 2. Created Database and Schema
I initialized the data environment and defined a structured table for country data with specific constraints.

- Created the world database: CREATE DATABASE world;
- Defined the country table: CREATE TABLE world.country (Code CHAR(3), Name CHAR(52), Conitinent ENUM(...), Population INT, PRIMARY KEY (Code));

### 3. Modified Table Structure
I updated the table schema using the ALTER command to ensure data accuracy and correct naming errors.

- Fixed a typographical error in the column name: ALTER TABLE world.country RENAME COLUMN Conitinent TO Continent;
- Verified the updated columns: SHOW COLUMNS FROM world.country;

### 4. Managed Resource Lifecycle
I practiced proper resource cleanup by removing tables and databases once the tasks were completed.

- Dropped the secondary city table: DROP TABLE world.city;
- Dropped the country table: DROP TABLE world.country;
- Deleted the entire world database: DROP DATABASE world;

## Skills Demonstrated
- Cloud Computing: Amazon EC2, AWS Systems Manager (Session Manager)
- Database Management: MySQL, Relational Database Design
- SQL Proficiency: DDL (Data Definition Language) commands: CREATE, ALTER, DROP, SHOW
- Linux Administration: CLI navigation and root privilege management

# Agile Data Management with Amazon DynamoDB

## Lab Overview
I implemented a serverless NoSQL database solution using Amazon DynamoDB to manage a dynamic music library. This project highlighted the core advantages of NoSQL: high-speed performance, horizontal scalability, and a "schemaless" flexible data model.

## Key Achievements & Technical Milestones

### 1. NoSQL Table Architecture
* **Primary Key Design:** Engineered a composite primary key consisting of a **Partition Key** (Artist) and a **Sort Key** (Song). This design ensures unique item identification and optimized data distribution across DynamoDB partitions.
* **High Availability:** Leveraged DynamoDB's fully managed infrastructure to provide consistent, single-digit millisecond latency at scale.

### 2. Flexible Schema Implementation
* **Dynamic Attribute Loading:** Demonstrated NoSQL flexibility by entering items with varying attributes (e.g., adding `Genre` to one record and `LengthSeconds` to another) without requiring a pre-defined schema.
* **Data Lifecycle Management:** Performed real-time CRUD (Create, Read, Update, Delete) operations, including modifying existing item attributes and performing targeted data updates.

### 3. Optimized Data Retrieval Strategies
* **High-Efficiency Querying:** Implemented **Query** operations to retrieve specific records using primary keys, utilizing DynamoDB’s underlying indexing for maximum speed.
* **Advanced Filtering (Scanning):** Executed **Scan** operations with specific filters (e.g., filtering by `Year`) to demonstrate data retrieval across non-indexed attributes.
* **Performance Analysis:** Evaluated the efficiency trade-offs between indexed Queries (faster, lower cost) and table-wide Scans (slower for large datasets).

### 4. Resource Governance
* **Clean-Up & Cost Control:** Practiced cloud hygiene by decommissioning resources (Table deletion) upon project completion to prevent unnecessary storage costs.

---
**Tech Stack:** Amazon DynamoDB, NoSQL, AWS Management Console.

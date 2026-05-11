# Advanced Data Organization with SQL (GROUP BY & Window Functions)

**Primary Domain:** Data Analytics / Database Management


**Key Concepts:** Aggregate Functions, Window Functions (`OVER`), Data Ranking

---

### OVERVIEW
In this project, I acted as a Data Analyst for a database operations team to perform complex regional population analysis. Using a relational database (`world`), I engineered advanced SQL queries to transform raw data into structured insights. I focused on the mechanical differences between the `GROUP BY` clause (for aggregation) and the `OVER` clause (for windowing and ranking).



### CORE MILESTONES

#### 1. Database Environment & Connection
* **Terminal Access:** Established a secure session to the **Command Host** via AWS Systems Manager Session Manager.
* **Database Authentication:** Authenticated with the MySQL server using CLI-based credentials to access the `world` database schema (comprising `city`, `country`, and `countrylanguage` tables).

#### 2. Aggregating Data with GROUP BY
* **Regional Summarization:** Developed queries using the `SUM()` aggregate function paired with `GROUP BY` to calculate the total population of specific regions (e.g., "Australia and New Zealand").
* **Data Filtering:** Applied `WHERE` clauses to refine datasets before aggregation, ensuring precision in regional reporting.

#### 3. Advanced Analysis with Window Functions (OVER)
* **Running Totals:** Engineered complex `SELECT` statements using the `OVER(partition by ...)` clause. This allowed for the calculation of "Running Totals" across countries while maintaining individual record visibility—a task impossible with standard `GROUP BY`.
* **Statistical Ranking:** Implemented the `RANK()` window function to assign numerical positions to countries based on population metrics. This is critical for identifying regional outliers and leading metrics.

#### 4. The "Largest to Smallest" Challenge
* **Solution Engineering:** Designed a final optimized query to rank every country globally, partitioned by their respective regions, and ordered by population in descending order.
* **SQL Logic:**
  ```sql
  SELECT Region, Name, Population, 
  RANK() OVER(partition by Region ORDER BY Population desc) as 'Ranked' 
  FROM world.country ORDER BY Region, Ranked;

## 🌱 SQL Learning 

*This repository contains my learnings about SQL, Query Optimization, and practice problems I've explored with using PostgreSQL.  Attached, to this repository is my SQL practice queries and take-aways.  Ths file Practice Queries contains queries from [w3resource.com](https://www.w3resource.com/sql-exercises/sql-joins-exercises.php).*

----
<h3 align="center">
    PART I:  SQL Query Optimization - A Summary of Best Practices
</h3>

1.	Try to use **SELECT on specific columns** instead of SELECT * (known as select all)

2.	**Avoid SELECT DISTINCT**, which can remove duplicates, by selecting more unique columns.  This practice can help decrease processing power.

3.	Use **INNER JOIN** instead of the WHERE clause when joining tables.  Using WHERE to join tables on a common columns performs a Cartesian Product / Cross Join, which can be a costly operation to especially in larger databases.

4.	Avoid using too many JOIN clauses on multiple tables as this can result in costly performance.  Instead try to split lengthy queries up and join them later.

5.	It is more efficient to filter a query based for conditions using a WHERE clause, unless there is a need to filter on an aggregate field, in which case the HAVING clause should be used.  This is in turn due to SQL Order of Operations.

6.	**Use EXISTS()** instead of COUNT().  EXISTS clause only runs until it locates the records first entry, saving both time and performance issues.

7.	It is more efficient to **use wildcard characters at the end of phrases.**  Instead of ‘%Char%’ you should use ‘Char%’ , which limits the amount of searching required by the database.

8.	Use **LIMIT clause to sample query** output if running a query for the first time, especially on a large database.  In this manner, the returns returned can ensure the query was correct or whether it needs editing.   Instead of LIMIT, the FETCH clause can also be used given its standardization from 2008, as not all RDBMS are capable of recognizing LIMIT.

9.	**Avoid using multiple OR clauses** within 1 given query, as this can lead to poor performance.  Instead split the query into SELECT statements and combine them use the UNION clause

10.	Preview a query's execution plan and estimated costs with an **EXPLAIN clause** without having to run the actual query.

11.	Indexes – add indexes to reduce runtime taking in consideration disk space required.  It is just as important to know when to remove unused indexes or not create them.  

12.	**Run queries in off-peak hours**, especially if they contain the following:
  + Large Tables
  + CROSS JOINS
  + Looping statements
  + SELECT DISTINCT
  + Nested Subqueries
  + Wildcard Searches

#### *Credits/Research Sources: [Sisense](https://www.sisense.com/blog/8-ways-fine-tune-sql-queries-production-databases/), [Tek Tools](https://www.tek-tools.com/systems/sql-query-optimization), [devart](https://blog.devart.com/how-to-optimize-sql-query.html)*

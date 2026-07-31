SQL JOINS
Joins is one of the most important topics in SQL. It is used in normalized dataset.

normalized table:
- multiple tables
- reduces redundancy
- reduces the null values
- queries faster
- there are no problems while inserting/updating/deleting certain values only
- PK enseures unique records and FK establishes a relationship between two or more tables.

denormalized table:
-single table(multiple info on a single table)
-easy to query
- particular info keeps repeating making the DB slower.( eg.a single customer buys 3 different products.then there will be 3 different records of the same customer buying different products with the same customer_name and details)
- many null values while inserting values on certain columns only
- the older data also gets updated and deleted (there will be no record of the old info)

These are the problems we face while using a denormalized data this is why we prefer normalized data, and to query normalized data we use joins.

Joins is used to combine data from two or more tables based on a related column between them.By using joins, we can retrieve related information from different tables in a single query.

# SQL Joins

## 📖 Introduction

A JOIN is used to combine data from two or more tables based on a related column between them.

Joins are one of the most important SQL concepts because data in relational databases is often stored across multiple tables. By using joins, we can retrieve related information from different tables in a single query.

---

## Sample Tables

### Employee

| EmployeeID | EmployeeName | DepartmentID |
| ---------- | ------------ | ------------ |
| 1          | John         | 10           |
| 2          | Alice        | 20           |
| 3          | David        | 30           |

### Department

| DepartmentID | DepartmentName |
| ------------ | -------------- |
| 10           | HR             |
| 20           | Finance        |
| 40           | Sales          |

---

# 1. INNER JOIN

## Definition

An INNER JOIN returns only the rows that have matching values in both tables.

```sql
SELECT e.EmployeeName,
       d.DepartmentName
FROM Employee e
INNER JOIN Department d
ON e.DepartmentID = d.DepartmentID;
```



Only matching DepartmentIDs are returned.

Result:

| EmployeeName | DepartmentName |
| ------------ | -------------- |
| John         | HR             |
| Alice        | Finance        |

---

# 2. LEFT JOIN

## Definition

A LEFT JOIN returns all records from the left table and the matching records from the right table.

## Example

```sql
SELECT e.EmployeeName,
       d.DepartmentName
FROM Employee e
LEFT JOIN Department d
ON e.DepartmentID = d.DepartmentID;
```



All employees are returned. If no matching department exists, NULL is displayed.

---

# 3. RIGHT JOIN

## Definition

A RIGHT JOIN returns all records from the right table and matching records from the left table.

## Example

```sql
SELECT e.EmployeeName,
       d.DepartmentName
FROM Employee e
RIGHT JOIN Department d
ON e.DepartmentID = d.DepartmentID;
```


All departments are returned, even if no employee belongs to that department.

---

# 4. FULL OUTER JOIN

A FULL OUTER JOIN returns all records from both tables. If there is no match, NULL values are returned.



| Join Type       | Returns                                   |
| --------------- | ----------------------------------------- |
| INNER JOIN      | Matching rows only                        |
| LEFT JOIN       | All rows from left table + matching rows  |
| RIGHT JOIN      | All rows from right table + matching rows |
| FULL OUTER JOIN | All rows from both tables                 |



* Joins combine related data from multiple tables.
* INNER JOIN returns matching records only.
* LEFT JOIN preserves all rows from the left table.
* RIGHT JOIN preserves all rows from the right table.
* FULL OUTER JOIN returns all records from both tables.
* Joins are commonly used in reporting, analytics, and database applications.



© 2025 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

## **1. SQL Overview**

Before going into components, understand:

* SQL stands for **Structured Query Language**
* ANSI SQL is the **standard version**, on which vendors like MySQL, Oracle, PostgreSQL, SQL Server add extensions
* SQL is divided into multiple categories: **DDL, DML, DCL, TCL, DQL**

---

## **2. DDL (Data Definition Language)**

Used to **define and modify database structure**.

| Command    | Purpose                                | Example                                       |
| ---------- | -------------------------------------- | --------------------------------------------- |
| `CREATE`   | Create objects like tables, views, dbs | `CREATE TABLE emp(id INT, name VARCHAR(50));` |
| `ALTER`    | Modify structure                       | `ALTER TABLE emp ADD salary INT;`             |
| `DROP`     | Delete object permanently              | `DROP TABLE emp;`                             |
| `TRUNCATE` | Remove all rows, keep structure        | `TRUNCATE TABLE emp;`                         |
| `RENAME`   | Change object name                     | `RENAME TABLE emp TO employee;`               |

🔸 **Exam Tip**: Difference between `DROP` vs `TRUNCATE` vs `DELETE` is frequently asked.

---

## **3. DML (Data Manipulation Language)**

Used to **manipulate data in tables**.

| Command  | Purpose                          | Example                                    |
| -------- | -------------------------------- | ------------------------------------------ |
| `INSERT` | Add data                         | `INSERT INTO emp VALUES (1,'Amit',50000);` |
| `UPDATE` | Modify data                      | `UPDATE emp SET salary=60000 WHERE id=1;`  |
| `DELETE` | Remove rows                      | `DELETE FROM emp WHERE id=1;`              |
| `MERGE`  | Insert/update based on condition | *(Oracle/SQL Server)*                      |

---

## **4. DCL (Data Control Language)**

Used for **permissions and security**.

| Command  | Purpose           |
| -------- | ----------------- |
| `GRANT`  | Give privileges   |
| `REVOKE` | Remove privileges |

Example:

```sql
GRANT SELECT, INSERT ON emp TO user1;
REVOKE INSERT ON emp FROM user1;
```

---

## **5. TCL (Transaction Control Language)**

Manages **transactions** (group of SQL statements executed as a unit).

| Command           | Purpose                                            |
| ----------------- | -------------------------------------------------- |
| `COMMIT`          | Save changes permanently                           |
| `ROLLBACK`        | Undo changes                                       |
| `SAVEPOINT`       | Create points in transaction to rollback partially |
| `SET TRANSACTION` | Set transaction properties                         |

Example:

```sql
BEGIN;
UPDATE emp SET salary = 50000 WHERE id=2;
SAVEPOINT sp1;
UPDATE emp SET salary = 70000 WHERE id=3;
ROLLBACK TO sp1;
COMMIT;
```

---

## **6. Constraints and Their Types**

Applied on table columns to **restrict invalid data**.

| Constraint    | Purpose                       | Example                               |
| ------------- | ----------------------------- | ------------------------------------- |
| `NOT NULL`    | Disallows NULL                | `name VARCHAR(50) NOT NULL`           |
| `UNIQUE`      | No duplicates                 | `email VARCHAR(100) UNIQUE`           |
| `PRIMARY KEY` | Unique + Not Null             | `id INT PRIMARY KEY`                  |
| `FOREIGN KEY` | Refers to PK of another table | `dept_id INT REFERENCES dept(id)`     |
| `CHECK`       | Validates condition           | `salary INT CHECK(salary > 0)`        |
| `DEFAULT`     | Auto assigns value            | `status VARCHAR(10) DEFAULT 'active'` |

**Exam Question**: Difference between PRIMARY KEY vs UNIQUE.

---

## **7. SQL Operators**

Types:

* **Arithmetic**: `+ - * / %`
* **Comparison**: `= != > >= < <=`
* **Logical**: `AND OR NOT`
* **Special**: `IN`, `BETWEEN`, `LIKE`, `IS NULL`, `EXISTS`, `ANY`, `ALL`

Example:

```sql
SELECT * FROM emp WHERE salary BETWEEN 30000 AND 60000;
```

---

## **8. SQL Functions**

### 🔹 Built-in functions:

1. **Aggregate Functions**
   `COUNT(), SUM(), AVG(), MAX(), MIN()`
2. **String Functions**
   `UPPER(), LOWER(), LENGTH(), CONCAT(), SUBSTR()`
3. **Date Functions**
   `NOW(), SYSDATE(), DATEADD(), DATEDIFF()`
4. **Math Functions**
   `ROUND(), CEIL(), FLOOR(), ABS()`

Example:

```sql
SELECT dept_id, AVG(salary) FROM emp GROUP BY dept_id;
```

---

## **9. Clauses in SQL**

| Clause         | Purpose                            |
| -------------- | ---------------------------------- |
| `WHERE`        | Filter rows before grouping        |
| `GROUP BY`     | Group rows for aggregate functions |
| `HAVING`       | Filter after grouping              |
| `ORDER BY`     | Sort results                       |
| `LIMIT/OFFSET` | Fetch N rows                       |

Order of execution → **FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY**

---

## **10. Joins and Their Types**

| Type           | Returns                       |
| -------------- | ----------------------------- |
| **INNER JOIN** | Matching rows only            |
| **LEFT JOIN**  | All left + matching right     |
| **RIGHT JOIN** | All right + matching left     |
| **FULL JOIN**  | All rows, matched + unmatched |
| **SELF JOIN**  | Join table with itself        |
| **CROSS JOIN** | Cartesian product             |

Example:

```sql
SELECT e.name, d.dept_name
FROM emp e
INNER JOIN dept d ON e.dept_id = d.id;
```

---

## **11. Subqueries**

A query inside another query.

Types:
Single Row
Multiple Row
Correlated Subquery
Nested Subquery

Example:

```sql
SELECT name FROM emp WHERE salary > (SELECT AVG(salary) FROM emp);
```

---

## **12. Views and Indexes**

### 🔹 Views

Virtual table (stored query).

```sql
CREATE VIEW high_salary AS
SELECT name, salary FROM emp WHERE salary > 60000;
```

### 🔹 Index

Speeds up searching on large tables.

```sql
CREATE INDEX idx_salary ON emp(salary);
```

**Exam Trick**: Indexes **slow down** `INSERT/UPDATE/DELETE` because index must also be updated.

---

## **FINAL EXAM STRATEGY**

✔ Practice `CREATE TABLE`, `JOIN`, `GROUP BY`, `SUBQUERY` queries
✔ Learn differences (DROP vs TRUNCATE vs DELETE, UNION vs UNION ALL, etc.)
✔ Solve minimum **50 SQL MCQs** + 20 case-based query questions
✔ Use platforms like:

* HackerRank SQL
* LeetCode SQL
* W3Schools Try-SQL
* InterviewBit SQL
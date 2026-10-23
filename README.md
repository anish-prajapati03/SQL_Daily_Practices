# SQL Daily Practices

A collection of SQL practice queries and solutions covering fundamental to advanced SQL concepts. This repository is designed to strengthen SQL skills through hands-on practice, problem-solving, and real-world scenarios.

## 📚 Topics Covered

- **Basic SQL Queries** – `SELECT`, `WHERE`, `DISTINCT`, `ORDER BY`, `LIMIT`
- **Filtering & Operators** – `AND`, `OR`, `IN`, `BETWEEN`, `LIKE`, `NOT IN`
- **Aggregate Functions** – `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`
- **Grouping Data** – `GROUP BY`, `HAVING`
- **SQL Joins** – `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN`
- **Subqueries** – Nested queries, `IN`, `NOT EXISTS`, and finding the second-highest value
- **Common Table Expressions (CTEs)** – Using the `WITH` clause to simplify complex queries
- **Window Functions** – `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `PARTITION BY`
- **Real-World SQL Problems** – Employee data, customer orders, salary analysis, and data filtering

## 📂 Repository Structure

```text
SQL_Daily_Practices/
│
│   ├── Basic_Queries
│   ├── Aggregate_Functions
│   ├── Joins
│   ├── Subqueries
│   ├── CTE_Queries
│   └── Window_Functions
│
└── README.md
```

*Note: The structure above represents the planned organization of topics. Actual files and folders may differ.*

## 🎯 Objectives

- Build a strong foundation in SQL.
- Practice writing efficient and readable SQL queries.
- Understand data retrieval, filtering, grouping, and joining.
- Solve SQL interview questions commonly asked in technical interviews.
- Improve logical thinking and database query skills.
- Track continuous learning through daily SQL practice.

## 💻 Sample SQL Queries

### 1. Find the second-highest distinct salary

```sql
SELECT MAX(salary) AS second_highest_salary
FROM employees
WHERE salary < (
    SELECT MAX(salary)
    FROM employees
);
```

### 2. Count employees in each department

```sql
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department;
```

### 3. Find employees earning above the average salary

```sql
SELECT first_name, salary
FROM employees
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
);
```

### 4. Use a CTE to find the minimum salary by department

```sql
WITH dept_min AS (
    SELECT department, MIN(salary) AS min_salary
    FROM employees
    GROUP BY department
)
SELECT e.first_name, e.department, e.salary, d.min_salary
FROM employees e
JOIN dept_min d
    ON e.department = d.department;
```

## 🛠️ Tools & Technologies

- **Language:** SQL
- **Concepts:** Relational databases, querying, aggregation, joins, and analytical functions
- **Version Control:** Git and GitHub

## 📈 Learning Progress

This repository is continuously updated with new SQL queries, practice problems, and solutions as I progress from basic SQL to advanced concepts.

## 🤝 Contributions

Suggestions, improvements, and alternative SQL solutions are welcome. Feel free to fork this repository and practice along.

## 👨‍💻 Author

**Anish Prajapati**

GitHub: [anish-prajapati03](https://github.com/anish-prajapati03)

---

⭐ If you find this repository useful, consider giving it a star!

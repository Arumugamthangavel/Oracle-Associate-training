# Oracle Associate Training - Day 3

Today I started learning the **main types of SQL commands** and practiced basic table operations.

## SQL Command Categories

SQL commands are mainly divided into:

1. DDL - Data Definition Language
2. DML - Data Manipulation Language
3. DCL - Data Control Language
4. TCL - Transaction Control Language
5. DQL - Data Query Language

---

## 1. DDL - Data Definition Language

DDL is used to define and modify the structure of database objects such as tables.

Commands learned:

- `CREATE`
- `ALTER`
- `DROP`
- `TRUNCATE`
- `RENAME`

### CREATE

Used to create a new table.

```sql
CREATE TABLE employee (
    emp_id NUMBER,
    emp_name VARCHAR2(50),
    salary NUMBER
);
```

### ALTER

Used to modify an existing table structure, such as adding or changing a column.

```sql
ALTER TABLE employee
ADD department VARCHAR2(50);
```

### DROP

Used to remove a table completely.

```sql
DROP TABLE employee;
```

It removes the table and its data.

### TRUNCATE

Used to remove all rows from a table while keeping the table structure.

```sql
TRUNCATE TABLE employee;
```

### RENAME

Used to change the name of a table.

```sql
RENAME employee TO employees;
```

---

## 2. DML - Data Manipulation Language

DML is used to work with the data stored inside tables.

Commands learned:

- `INSERT`
- `UPDATE`
- `DELETE`
- `MERGE`

### INSERT

Adds new records to a table.

```sql
INSERT INTO employee
VALUES (101, 'Arun', 25000);
```

### UPDATE

Modifies existing data.

```sql
UPDATE employee
SET salary = 30000
WHERE emp_id = 101;
```

### DELETE

Removes selected rows from a table.

```sql
DELETE FROM employee
WHERE emp_id = 101;
```

### MERGE

`MERGE` can be used to insert new data or update existing data depending on whether a matching record exists.

---

## 3. TCL - Transaction Control Language

TCL is used to manage transactions.

Commands learned:

- `COMMIT`
- `ROLLBACK`
- `SAVEPOINT`

### COMMIT

Makes the changes permanent.

```sql
COMMIT;
```

### ROLLBACK

Reverts uncommitted changes.

```sql
ROLLBACK;
```

### SAVEPOINT

Creates a point inside a transaction that we can return to.

```sql
SAVEPOINT point1;

ROLLBACK TO point1;
```

---

## 4. DCL - Data Control Language

DCL is related to permissions and access control in the database.

Main commands:

- `GRANT`
- `REVOKE`

### GRANT

Gives privileges to a user.

```sql
GRANT SELECT ON employee TO user1;
```

### REVOKE

Removes previously given privileges.

```sql
REVOKE SELECT ON employee FROM user1;
```

---

## 5. DQL - Data Query Language

DQL is used to retrieve data from the database.

The main command is:

```sql
SELECT
```

Example:

```sql
SELECT * FROM employee;
```

We can also select specific columns:

```sql
SELECT emp_id, emp_name
FROM employee;
```

---

## Table Creation Practice

I also practiced creating a table by defining columns and their data types.

Basic structure:

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype
);
```

Example:

```sql
CREATE TABLE employee (
    emp_id NUMBER,
    emp_name VARCHAR2(50),
    salary NUMBER,
    created_date DATE
);
```

I also started understanding how each column is defined with its appropriate data type.

---

## Important Difference

### DROP vs TRUNCATE vs DELETE

| Command | What it does |
|---------|--------------|
| `DROP` | Removes the table itself along with its data |
| `TRUNCATE` | Removes all rows but keeps the table structure |
| `DELETE` | Removes selected rows and can use `WHERE` |

This is an important difference when working with tables.

---

## What I Learned Today

Today I learned the basic classification of SQL commands and started practicing table operations.

Main topics:

- DDL
- DML
- DCL
- TCL
- DQL
- CREATE
- ALTER
- DROP
- TRUNCATE
- RENAME
- INSERT
- UPDATE
- DELETE
- MERGE
- COMMIT
- ROLLBACK
- SAVEPOINT
- GRANT
- REVOKE
- SELECT

More SQL practice and concepts will be added as the training continues.

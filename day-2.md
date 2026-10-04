# Oracle Associate Training - Day 2

Today I continued with Oracle database basics and learned more about **data types, database objects, constraints, indexes and views**.

## Data Types

Data types define what kind of data can be stored in a column.

Some commonly used Oracle data types:

- `VARCHAR2` - variable length character data
- `CHAR` - fixed length character data
- `NUMBER` - numeric values
- `DATE` - date and time values
- `TIMESTAMP` - date and time with more precision
- `CLOB` - large character/text data
- `BLOB` - large binary data

### VARCHAR2 vs CHAR

- `VARCHAR2` stores variable length characters.
- `CHAR` stores fixed length characters.

`VARCHAR2` is commonly used for names, addresses, emails and other normal text values.

---

## Database Objects

Database objects are the structures used to store, manage and access data.

The objects covered so far:

- Tables
- Sequences
- Synonyms
- Indexes
- Views

### Table

A table is used to store data in rows and columns.

```sql
CREATE TABLE employee (
    emp_id NUMBER,
    emp_name VARCHAR2(50),
    salary NUMBER
);
```

### Sequence

A sequence is used to generate numbers automatically, usually for IDs.

```sql
CREATE SEQUENCE employee_seq
START WITH 1
INCREMENT BY 1;
```

```sql
SELECT employee_seq.NEXTVAL FROM dual;
```

### Synonym

A synonym is another name (alias) for a database object.

```sql
CREATE SYNONYM emp FOR employee;
```

It can make accessing an object easier without using its original name.

---

## Constraints

Constraints are rules applied to table columns to maintain data integrity.

The main constraints learned:

### Primary Key

- Uniquely identifies each row.
- Does not allow duplicate values.
- Does not allow NULL values.

### Unique

- Does not allow duplicate values in a column.

### Foreign Key

- Creates a relationship between two tables.
- Refers to a key in another table.

### NOT NULL

- Does not allow a column to contain NULL values.

### CHECK

- Allows values only when a specified condition is true.

Example:

```sql
CREATE TABLE employee (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50) NOT NULL,
    salary NUMBER CHECK (salary > 0)
);
```

---

## Indexes

An index is used to improve the speed of data retrieval.

A simple way to understand it is to think about the index of a book. Instead of checking every page, the index helps us find the required information faster.

Indexes can improve query performance, but they also require storage and can add overhead when data is modified.

---

## Views

A view is a virtual representation of data based on a query.

Views can be used to show only the required data without directly working with the original table every time.

Types learned so far:

- Simple View
- Complex View
- Materialized View

### Simple View

Usually based on a single table.

### Complex View

Can involve multiple tables, joins, functions or other complex operations.

### Materialized View

Stores the result of a query physically and can be useful when the same expensive query result is needed repeatedly.

---

## What I Learned Today

Today I mainly understood:

- Different Oracle data types
- What database objects are
- How sequences are used
- What synonyms are
- Why constraints are important
- Different types of constraints
- Why indexes are used
- Basics of views and their types

Still more topics are left to learn, so I will continue adding them as the training progresses.
"""

path = Path("/mnt/data/Day-02-README.md")
path.write_text(content, encoding="utf-8")
print(path)

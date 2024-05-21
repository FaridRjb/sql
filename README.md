# SQL

## What is SQL?

SQL stands for Structured Query Language. SQL will allow you to interact with the data stored in a database.

## Records and Fields

Each *database* has at least one *table*, and each table has *records (rows)* amd *fields (columns)*.

<p align="center">
<img src="https://lecontent.sololearn.com/material-images/8a1aa66040d74383b466acd6a9da49f5-1.01.07.png" alt="Records and fields." width="500"/>
</p>

## Schema

A schema is a visual representation of how a database is organized, showing its tables, fields and keys.

## Header

The name of the fields on the first row are called *header* and the corresponding row is called the *header* row.

## Getting a Field

We have a table named *tb*. It has fields *f1*, *f2* and *f3*. The data stored in the field *f2* can be accessed through:

```sql
SELECT f2
FROM tb
```

Multiple fields can be selected by separating the field with commas.

```sql
SELECT f2, f3
FROM tb
```

The * symbol allows you to select all the fields in a table.

## Query

The term for a request of information from a database is *query*.

## Structured and Unstructured Data

Data that can be stored in tables is called structured data. <!-- TODO: clarify -->

Unstructured data is information that is difficult to store in tables. <!-- TODO: clarify -->

## Relational database

<p align="center">
<img src="https://lecontent.sololearn.com/material-images/a51f8d8a65184b379a2356e0d09ed0c4-sql13.png" alt="Relational database." width="500"/>
</p>

A relational database stores information in tables. The different tables in a relational database are connected to each other using fields which are called *keys*.

## Comments

In an SQL query, `--` can be used to write comments.

## Block Comments

Block comments can be opened using `/*` and closed using `*/`.

### Naming Conventions

Data professionals use uppercase for the SQL command words and lowercase for tables and fields names.

## Sorting

The data can be sorted according to the values in a field by adding the following line after the name of the table:

```sql
ORDER BY f2
```

The extracted data will be sorted in ascending order by default. The keywords `ASC` and `DESC` should be added after the name of the field.

## Limit

The `LIMIT` keyword can be used to limit the number of the records, followed by an integer.

> [!NOTE]
> The correct sequence of ordering and limiting the number of extracted records is `ORDER` and then `LIMIT`.

## Offset

<p align="center">
<img src="https://lecontent.sololearn.com/material-images/d7120b3b2d334150bc30a0685796f1c4-2.03.11.png" alt="Offset and limit." width="500"/>
</p>

The `OFFSET` keyword should be added after the value of the `LIMIT` keyword, followed by an integer. For example:

```sql
LIMIT 3 OFFSET 2
```

## Data Types

Data types can be *string*, *numerical*, *boolean* (`True/False`) and *date/time*.

## As

The values in some fields of a table can be manipulated and be assigned to a newly defined field. For example:

```sql
SELECT f1, f2+f3 AS TOTAL
FROM tb
```

The operators `+` and `*` <!-- TODO: sure? -->

Text data can be merged using the `CONCAT` function. For instance:

```sql
SELECT CONCAT(f1, f2) AS merged
FROM tb
```

## Filtering Data / Conditions

A condition can be applied on the data using the `WHERE` keyword. Values in a field can be filtered by the following line:

```sql
WHERE f2 = 'value'
```

> [!NOTE]
> Strings should be surrounded with quotation marks.

The example above can be applied to text data. For numeric data, the comparison operators `>`, `>=`, `<`, `<=`, `=` and `<>` (not equal) can be used. The `<>` operator can also be used for string data.

## Like

The `LIKE` keyword is used with the `WHERE` command to search for patterns in string values. It can be put where the mathematical operators are used.

## Patterns

The `%` special symbol is known as a *wildcard* and is used to create patterns. For example,

```sql
WHERE email LIKE '%@gmail.com'
```

returns the emails ending with `@gmail.com`.

## Underscore

The underscore symbol `_` is another wildcard and represents 1 single character only.

## Semicolon

Multiple queries can be separated using `;` at the end of the last line of each query.

## Lower and Uppercase

Strings in a field can be uppercased or lowercased using the functions `LOWER()` and `UPPER()`, respectively.

```sql
SELECT LOWER(f2), UPPER(f3)
FROM tb
```

> [!TIP]
> The `LOWER` can be used to perform a not case-insensitive search using a pattern in lowercase.

## Aggregation

### Maximum and Minimum

The maximum value can be obtained using the `MAX()` function, and `MIN()` for the minimum.

```sql
SELECT MAX(f2)
FROM tb;

SELECT MIN(f2)
FROM tb;
```

> [!NOTE]
> All of the following aggregation operations can be performed in the same manner.

### Count

`COUNT()` counts the number of records

### Sum

`SUM()` produces the total sum of the values in a numerical field.

### Average

`AVG()` calculates the average value.

> [!NOTE]
> When running queries that involve different operations, filtering happens first.

## Data Collection

### API

*Servers* are computers that are always listening for requests of information. You can request information from a database server through an *API* (Application Programming Interface).

### Web Scraping

*Web scraping* allows you to extract information from websites. 

## Grouping

`GROUP BY` allows you to organize similar data into categories. It's combined with aggregations to compute key metrics for a group of records.

```sql
SELECT f1, AVG(f2)
FROM tb
GROUP BY f1
```

<p align="center">
<img src="https://lecontent.sololearn.com/material-images/c142abf6ac07419fa752acf9e1d3fbaf-SQL4.03.04.png" alt="Filtering, grouping and aggregation." width="500"/>
</p>

> [!NOTE]
> When a query contains both `WHERE` and `GROUP BY`, data is filtered first, then grouped.

## Having

`HAVING` allows you to filter data that has been grouped.

> [!NOTE]
> When a query contains both GROUP BY and HAVING, data is grouped first, then filtered.

## Distinct

The duplicated records can be identified using the following query:

```sql
SELECT f1, COUNT(f1)
FROM tb
GROUP BY f1
HAVING COUNT(f1) > 1;
```

Use `DISTINCT` to eliminate duplicate values.

```sql
SELECT DISTINCT f1
FROM tb
```

## Null

`NULL` is used to indicate that a data value is missing and does not exist in the database. `NULL` values are not shown in result tables.

Use `IS NULL` in combination with `WHERE` to find missing values.

```sql
SELECT * 
FROM tb 
WHERE f2 IS NULL
```

Extract non-null values using `IS NOT NULL`.

```sql
SELECT * 
FROM tb 
WHERE f2 IS NOT NULL
```

## Logical Operations

Operations involving boolean values are known as *logical operations*.

### And

<p align="center">
<img src="https://lecontent.sololearn.com/material-images/f3aadf1b0f254c9b9c4583e42d806694-Frame27192.png" alt="And." width="500"/>
</p>

The *AND operation* results in a True value only when all the values are True at the same time.

### Or

<p align="center">
<img src="https://lecontent.sololearn.com/material-images/887e49a38f744ccb8690e0238a8ded4c-4.06.15.png" alt="Or." width="500"/>
</p>

The *OR logical operation* results in a True value if at least one of the conditions is True.

## References

- [Introduction to SQL](https://www.sololearn.com/en/learn/courses/sql-introduction)

# SQL

## What is SQL?

SQL stands for Structured Query Language. SQL will allow you to interact with the data stored in a database.

## Records and Fields

Each *database* has at least one *table*, and each table has *records (rows)* amd *fields (columns)*.

![Record and Field in a table.](https://lecontent.sololearn.com/material-images/8a1aa66040d74383b466acd6a9da49f5-1.01.07.png)

## Schema

A schema is a visual representation of how a database is organized, showing its tables, fields and keys.

## Header

The name of the fields on the first row are called *header* and the corresponding row is called the *header* row.

## Getting a Field

We have a table named *tb*. It has fields *f1*, *f2* and *f3*. The data stored in the field *f2* can be acccessed through:

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

![](https://lecontent.sololearn.com/material-images/a51f8d8a65184b379a2356e0d09ed0c4-sql13.png)

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

![](https://lecontent.sololearn.com/material-images/d7120b3b2d334150bc30a0685796f1c4-2.03.11.png)

The `OFFSET` keyword should be added after the value of the `LIMIT` keyword, followed by an integer. For example:

```sql
LIMIT 3 OFFSET 2
```

## Data Types

These types can be `text`, `numeric`. <!-- TODO: clarify -->

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

Strings in a field can be uppercased or lowecased using the functions `LOWER()` and `UPPER()`, respectively.

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

## References

- [Introduction to SQL](https://www.sololearn.com/en/learn/courses/sql-introduction)

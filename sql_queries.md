## SELECT
`SELECT` is used to select data from a database. The data returned is stored in a result table, called the result-set.

**Modifiers**\
`SELECT DISTINCT` is used to return distinct values - each row in the result-set is unique from the rest of the other rows.\
`SELECT ALL` specifies that duplicates can appear in the result set - essentially a more explicitly stated version of `SELECT` because `ALL` is the default.\
`SELECT TOP X` where `X` is a nonnegative integer number gets the first `X` records.\
`SELECT TOP X PERCENT` where `X` is an integer or decimal value between 0 and 100 gets the first `X`% of records.

**Functions**\
`SELECT MIN()` gets the smallest value of a selected column.\
`SELECT MAX()` gets the largest value of a selected column.\
`SELECT COUNT()` gets the number of rows of a selected column.\
`SELECT AVG()` gets the average of all values in a selected column.\
`SELECT SUM()` gets the sum of all values in a selected column.

**Notes:**
- `SELECT *` selects all columns from the table(s) to be returned
- If selecting a column name from tables that contain the same column name, the table name must be prefixed before the column name in the select statement in order to eliminate ambiguity and explicitly specify which column is to be returned e.g. `SELECT Table1.Column1 FROM Table1, Table2`

## FROM
`FROM` is used to identify which table(s) to pull the data from.

**Notes:**
- if selecting from multiple tables, the returned set is a merged version of the data in all tables where each row in each table is matched with each other in every possible combination assuming no other joins and no where clauses that could modify the result
- can be used to help retrieve data in nested subqueries - since queries return result tables, these result tables can be referenced by `FROM` in order to pass data up to higher levels e.g. `SELECT Subtable.Column1 FROM (SELECT * FROM Table1) AS Subtable`

## WHERE
The `WHERE` clause is used to filter and extract records based on certain conditions.

**Modifiers**\
`=` equals\
`>` greater than\
`<` less than\
`>=` greater than or equal to\
`<=` less than or equal to\
`<>` not equal\
`BETWEEN` between a specified range (used with `AND`)\
`LIKE` search for a string pattern\
`IN` to specify possible values for a column (used with a set of values or a nested query)

**Conjunctions**\
`AND` is used to chain multiple conditions together that must be true\
`OR` is used to chain multiple conditions together where only one of these conditions need to be true

**Negators**\
`NOT` is used in front of a modifier to negate its effect

**Notes:**
- `IN` can also be used to create nested subqueres like `FROM` e.g. `SELECT * FROM Table1 WHERE Column1 IN (SELECT * FROM Table1)

## AS
`AS` is used to name or rename columns or tables e.g. `SELECT Column1 AS Name FROM Table1`.

## ORDER BY
`ORDER BY` sorts the result-set in ascending or descending order.

**Modifiers**\
`ASC` sorts in ascending order - the default if not explicitly stated. (usage `ORDER BY Column1 ASC`).\
`DESC` sorts in descending order. (usage `ORDER BY Column1 DESC`)

**Notes:**
- multiple columns can be listed separated by commas - data will be sorted primarily by the first column, then the second, and so on
- Each individual column can be specified to be sorted in ascending or descending order if desired

## GROUP BY
`GROUP BY` groups rows that have the same values into summary rows - generally used with aggregate functions like `COUNT()`.

**Notes:**
- instead of listing column names to group by, numbers from 1 to # of selected columns can be written instead

Useful links: https://www.w3schools.com/sql/default.asp

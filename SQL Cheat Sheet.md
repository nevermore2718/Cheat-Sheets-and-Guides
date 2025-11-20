## Basic SQL Syntax

| Command | Syntax | Description |
| ------- | ------ | ----------- |
| ALTER Table | ALTER TABLE table_name ADD column_name datatype; | Add columns of a specified datatype to a table in database |
| AS | SELECT column_name AS 'Alias' FROM table_name; | A keyword in SQL to rename a column or table using an alias name |
| CASE | SELECT column_name, CASE WHEN condition THEN 'Result_1' WHEN condition THEN 'Result_2' ELSE 'Result_3' END FROM table_name; | Create different output inside a SELECT statement |
| CREATE TABLE | CREATE TABLE table_name (column_1 datatype, column_2 datatype, column_3 datatype); | Create a new table in a database and specify the name of the table and columns of a specified datatype inside it |
| DELETE | DELETE FROM table_name WHERE some_column = some_value; | Remove the row from a table |
| HAVING | SELECT column_name; COUNT(*) FROM table_name GROUP BY column_name HAVING COUNT (*) > value; | Use it like the WHERE keyword in aggregating functions such as GROUP BY |
| INSERT | INSERT INTO table_name (column_1, column_2, column_3); | Add new rows to table with specified values | 
| SELECT | SELECT column_name FROM table_name; | Fetch data from a database; the column_name can be a function applied to an existing column |
| SELECT DISTINCT | SELECT DISTINCT column_name FROM table_name; | Return unique, non-repeating values in specified columns |
| UPDATE | UPDATE table_name SET some_column = some_value WHERE some_column = some_value; | Edit rows in a table |
| WITH | WITH temporary_name AS (SELECT * FROM table_name) SELECT * FROM temporary_name WHERE column_name operator value; | Process the result of a query (SELECT * FROM table_name) stored in a temporary table referenced by the alias temporary_name |
| /* * / -- | /* multi-line comment explaining the code */ --single-line comment | Enclose comments: (From comments spanning several lines: /* */) (For comments on the same line as the command: --) |

### Data Types
Identifies how SQL will interact with the stored data. SQL is a strongly typed language.

## MySQL Data Types
MySQL has three main data types: string, numeric, and data and time.

### String
| Data Type | Description |
| ------- | ----------- |
| CHAR(size) | A fixed-length string: can contain letters, numbers, and special characters. The size parameter specifies the column length in characters, from 0 to 255. The default is 1. |
| VARCHAR(size) | A variable-length string: can contain letters, numbers, and special characters. The size parameter specifies the maximum string length in characters, from 0 to 65535 |
| BINARY(size) | Equal to CHAR() but stores binary byte strings. The size parameter specifies the column length in bytes. The default is 1. |
| VARBINARY(size) | Equal to VARCHAR() but stores binary byte strings. The size parameter specifies the maximum column length in bytes. |
| TINYBLOB | For BLOBs (Binary Large Objects). Max Length: 255 bytes |
| TINYTEXT | Hold a string with maximum length of 255 characters |
| TEXT(size) | Hold a string with a maximum length of 65,535 bytes |
| BLOB (size) | For BLOBs (Binary Large Objects). Hold up to 65,535 bytes of data. |
| MEDIUMTEXT | Hold a string with a maximum length of 16,777,215 characters |
| MEDIUMBLOB | For BLOBs (Binary Large Objects). Hold up to 16,777,215 bytes of data |
| LONGTEXT | Hold a string with a maximum length of 4,294,967,295 characters |
| LONGBLOB | For BLOBs (Binary Large Objects). Hold up to 4,294,967,295 bytes of data |
| ENUM (val1, val2, val3, ...) | A string object that can have only one value, chosen from a list of possible values. You can list up to 6535 values in an ENUM list. If you insert a value that is not in the list, you insert a blank value. SQL sorts the values in the order you enter them |
| SET (val1, val2, val3, ...) | A string object that can have 0 or more values, chosen from a list of possible values. You can list up to 64 values in a SET list. |

### Numeric
We leave the "Alias" blank if a daya type has no alias.

| Data Type | Alias | Description |
| ------- | ------ | ----------- |
| BIT(size) | | A bit-value type. The size parameter specifies the number of bits per value and can hold a value from 1 to 64. The default value for size is 1. |
| TINYINT(size) | | A tiny integer. The signed is from -128 to 127. The unsigned range is from 0 to 255. The size parameter specifies the maximum display width (which is 255) |
| BOOLEAN| BOOL| Zero = false, nonzero values = true |
| SMALLINT(size) | | A small integer. The signed range is from -32768 to 327767. The unsigned range is from 0 to 65535. The size parameter specifies the maximum display width (which is 255). |
| MEDIUMINT(size) | | A medium-sized integer. The signed range is from -8388608 to 8388607. The unsigned range is from 0 to 16777215. The size parameter specifies the maximum display width (which is 255).
INTEGER(size) | INT(size) | A medium-sized integer. The signed range is from -2147483648 to 2147483647. The unsigned range is from 0 to 4294967295. The size parameter specifies the maximum display width (which is 255) |
| BIGINT(size) | | A large integer. The signed range is from -9223372036854775808 to 92233772026854775807. The unsigned range is from 0 to 18446744073709551615. The size parameter specifies the maximum display width (which is 255) |
| FLOAT(size,d), DOUBLE(size,d), DOUBLE PRECISION(size,d) | | Floating point numnber. The parameter size specifies the total number of digits. The d parameter sets the number of digits. (Future MySQL versions beyond MySQL 8.0.17) will remove this syntax. |
| FLOAT (p) | | Floating point number. MySQL uses the p value to determine whether to use FLOAT or DOUBLE for the resulting data type. If p is from 0 to 24, the data type becomes FLOAT(). If p is from 25 to 53, the data type becomes DOUBLE(). |
| DECIMAL(size,d) | DEC(size,d) | Fixed-point number. The parameter size specifies the total number of digits. The d parameter sets the number of digits after the decimal point. The maximum number for size is 65. The maximum number for d is 30. The default value for size is 10. The default value for d is 0.|

All the numeric data types may have an extra option: UNSIGNED or ZEROFILL. If you add the UNSIGNED option, MySQL disallows negative values for the column. If you add the ZEROFILL option, MySQL automatically adds the UNSIGNED attribute to the column.

### Date and Time
Adding DEFAULT and ON UPDATE in the column definition helps you get automatic initialization and updating to the current data and time.

| Command | Description |
| ------- |  ----------- |
| DATE | Date, Format: YYYY,MM,DD. The suppored range is from '1000-01-01' to '9999-12-31' |
| DATETIME(fsp) | Date and time combination. Format: YYYY-MM-DD hh:mm:ss |
| TIMESTAP(fsp) | Timestamp. MySQL stores TIMESTAMP values as the number of seconds since the Unix epoch ('1970-01-01 00:00:00" UTC). Format: YYYY-MM-DD hh:mm:ss |
| TIME (fsp) | Time. Format: hh:mm:ss |
| YEAR | Year in four-digit format. MySQL 8.0 does not support a two-digit year format. |

## SQL Operators
| Command | Syntax | Description |
| ------- | ------ | ----------- |
| AND | SELECT column_name(s) FROM table_name WHERE column_1 = value_1 AND column_2 = value_2; | Combine two conditions |
| BETWEEN | SELECT column_name(s) FROM table_name WHERE column_name BETWEEN value_1 AND value_2; | Filter the result within a certain range |
| IS NULL | SELECT column_name(s) FROM table_name WHERE column_name IS NULL; | Check for empty values in conjection with the WHERE clause |
| IS NOT NULL | SELECT column_name(s) FROM table_name WHERE column_name IS NOT NULL; | Check for the absence of empty values in conjuction with the WHERE clause |
| LIKE | SELECT column_name(s) FROM table_name WHERE column_name LIKE pattern; | Search for a specific pattern in a column in conjunction with the WHERE clause |
| OR | SELECT column_name FROM table_name WHERE column_name = value_1 OR column_name = value_2; | Filter the result set to contain only the rows where either condition is TRUE |
| UNION | SELECT column_name(s) FROM table1 UNION SELECT column_name(s) FROM table2; | Combine the results of two or more SELECT statements and select only distinct values |
| UNION ALL | SELECT column_name(s) FROM table1 UNION ALL SELECT column_name(s) FROM table2; | Combine the result of two or more SELECT statements, allowing duplicate values|

## SQL Functions
Help compute and analyze the contents of database tables

| Command | Syntax | Description |
| ------- | ------ | ----------- |
| AVG() | SELECT AVG(column_name) FROM table_name; | Aggregate a numeric column and return its arithmetic mean, ignoring NULL values |
| CHAR_LENGTH() | SELECT CHAR_LENGTH(string) AS LengthOfString; | (MySQL) Return the length of a string in characters |
| COUNT() | SELECT COUNT(column_name) FROM table_name; | Take the name of a column as an argument and count the number of rows when the column is not NULL |
| FIRST() | SELECT FIRST(column_name) FROM table_name; | Return the first value of the selected column |
| Last() | SELECT LAST(column_name) FROM table_name; | Return the last value of the selected column |
| MAX() | SELECT MAX (column_name) FROM table_name; | Take at least one column as an argument and return the largest value amog them |
| MIN() | SELECT MIN(column_name) FROM table_name; | Take at least one column as an argument and return the smallest value among them |
| NULLIF() | SELECT NULLIF(expr1, expr2); | Return NULL if two expressions expr1, expr2 are equal. Otherwise, it returns the first expression. |
| ROUND() | SELECT ROUND(column_name, integer) FROM table_name; | Take the column name and an integer as an argument, and round the values in a column to the number of decimal places specified by an integer |
| SUM() | SELECT SUM(column_name) FROM table_name; | Return the sum of values from a particular column |
| VAR() | SELECT VAR(column_name) FROM table_name; | Return the statistical variance | 

## SQL Clauses
| Command | Syntax | Description |
| ------- | ------ | ----------- |
| LIMIT | SELECT column_name(s) FROM table_name LIMIT number; | Specify the maximum number of rows the result set must have |
| GROUP BY | SELECT column_name; COUNT(*) FROM table_name GROUP BY column_name; | Used for aggregate functions in collaboration with the SELECT statement |
| ORDER BY | SELECT column_name FROM table_name ORDER By column_name ASC / DESC; | Sort the result set by a particular column either numerically or alphabetically. ASC means "in ascending order;" DESC, "descending." |
| WHERE | SELECT column_name(s) FROM table_name WHERE column_name operator value; | Filter the result set to include the rows where the condition is TRUE | 

## SQL Joins
| Command | Syntax | Description |
| ------- | ------ | ----------- |
| INNER JOIN | SELECT column_name(s) FROM table_1 JOIN table_2 ON table_1.column_name = table_2.column_name; | Select records that have matching values in both tables |
| LEFT JOIN | SELECT column_name(s) FROM table_1 LEFT JOIN table_2 ON table_1.column_name = table_2.column_name; | Combine all records from the left side and any matching rows from the right table.LEFT OUTER JOIN and LEFT JOIN are the same. |
| RIGHT JOIN | SELECT column_name(s) FROM table_1 RIGHT JOIN table_2 ON table_1.column_name = table_2.column_name; | Combine all rows from the right side and any matching rows from the left table.RIGHT OUTER JOIN and RIGHT JOIN are the same. |
| FULL JOIN | SELECT column_name(s) FROM table1 FULL OUTER JOIN table2 ON table1.column_name = table2.column_name WHERE condition; | Return all records whether the records in the left (table1) and right (table2) tables match.FULL OUTER JOIN and FULL JOIN are the same. |

## SQL Constraints
Constraints are for specifying rules for data in a table.

The syntax is
```
[CREATE|ALTER] TABLE table_name (
column1 datatype constraint,
column2 datatype constraint,
column3 datatype constraint,
...
);
```

Common constraints in SQL:
| Command | Description |
| ------- | ----------- |
| NOT NULL | Ensure that a column cannot have a NULL value |
| UNIQUE | Ensure that all values in a column are different |
| PRIMARY KEY | A combination of NOT and UNIQUE: uniquely identifies each row in a table |
| FOREIGN KEY | Prevent actions that would destory links between tables |
| CHECK | Ensure that the values in a column satisfy a specifc condition |
| DEFAULT | Set a default value for column that contains no specified value |
| AUTO_INCREMENT | Allow te automatic generation of a unique number when inserting a new record into a table | 

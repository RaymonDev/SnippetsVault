## SQL

### Create a table
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
```

### SELECT all rows from a table
```sql
SELECT * FROM table_name;
```

### SELECT specific columns from a table
```sql
SELECT column1, column2 FROM table_name;
```

### Filter rows using WHERE clause
```sql
SELECT * FROM table_name WHERE column_name = value;
```

### Sort rows in ascending order
```sql
SELECT * FROM table_name ORDER BY column_name ASC;
```

### Sort rows in descending order
```sql
SELECT * FROM table_name ORDER BY column_name DESC;
```

### LIMIT the number of results
```sql
SELECT * FROM table_name LIMIT 10;
```

### Add a new row to a table
```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
```

### Update the data in a table
```sql
UPDATE table_name SET column1 = new_value WHERE column2 = condition;
```

### Delete a row from a table
```sql
DELETE FROM table_name WHERE column_name = value;
```

### COUNT the number of rows in a table
```sql
SELECT COUNT(*) FROM table_name;
```

### SUM values in a column
```sql
SELECT SUM(column_name) FROM table_name;
```

### AVERAGE values in a column
```sql
SELECT AVG(column_name) FROM table_name;
```

### GROUP BY and aggregate functions
```sql
SELECT column1, COUNT(column2) FROM table_name GROUP BY column1;
```

### JOIN two tables (INNER JOIN)
```sql
SELECT * FROM table1 INNER JOIN table2 ON table1.column = table2.column;
```

### LEFT JOIN
```sql
SELECT * FROM table1 LEFT JOIN table2 ON table1.column = table2.column;
```

### RIGHT JOIN
```sql
SELECT * FROM table1 RIGHT JOIN table2 ON table1.column = table2.column;
```

### FULL OUTER JOIN
```sql
SELECT * FROM table1 FULL OUTER JOIN table2 ON table1.column = table2.column;
```

### Add a new column to an existing table
```sql
ALTER TABLE table_name ADD column_name datatype;
```

### Rename a table
```sql
ALTER TABLE old_table_name RENAME TO new_table_name;
```

### Rename a column
```sql
ALTER TABLE table_name RENAME COLUMN old_column_name TO new_column_name;
```

### Create an INDEX on a column
```sql
CREATE INDEX index_name ON table_name (column_name);
```

### Remove an INDEX
```sql
DROP INDEX index_name;
```

### Retrieve unique values from a column
```sql
SELECT DISTINCT column_name FROM table_name;
```

### Filter rows using multiple conditions (AND)
```sql
SELECT * FROM table_name WHERE condition1 AND condition2;
```

### Filter rows using multiple conditions (OR)
```sql
SELECT * FROM table_name WHERE condition1 OR condition2;
```

### Use wildcards in LIKE
```sql
SELECT * FROM table_name WHERE column_name LIKE 'pattern%';
```

### Use a subquery WHERE clause
```sql
SELECT * FROM table_name WHERE column_name IN (SELECT column_name FROM another_table);
```

### Calculate a new column with an expression
```sql
SELECT column1, column2, column1 + column2 AS sum FROM table_name;
```

### Retrieve the current date and time
```sql
SELECT CURRENT_TIMESTAMP;
```

### Truncate a table (remove all rows)
```sql
TRUNCATE TABLE table_name;
```

### Case-insensitive search (using ILIKE in PostgreSQL)
```sql
SELECT * FROM table_name WHERE column_name ILIKE 'pattern%';
```

### Calculate the difference between two dates
```sql
SELECT DATEDIFF(end_date, start_date) AS date_difference FROM table_name;
```

### Create a temporary table
```sql
CREATE TEMPORARY TABLE temp_table AS SELECT * FROM table_name;
```

### Generate random numbers
```sql
SELECT RAND() AS random_number;
```

### Convert data types (from string to integer)
```sql
SELECT CAST(column_name AS INT) FROM table_name;
```

### Use COALESCE to handle NULL values
```sql
SELECT COALESCE(column_name, default_value) FROM table_name;
```

### Use the having clause with GROUP BY
```sql
SELECT column1, COUNT(column2) FROM table_name GROUP BY column1 HAVING COUNT(column2) > 1;
```

### Retrieve the Nth highest (or lowest) value in a column
```sql
SELECT DISTINCT column_name FROM table_name ORDER BY column_name DESC LIMIT 1 OFFSET N-1;
```

### Export query result to a CSV file (in MySQL)
```sql
SELECT * INTO OUTFILE 'file.csv' FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"' LINES TERMINATED BY '\n' FROM table_name;
```

### Create a VIEW
```sql
CREATE VIEW view_name AS SELECT column1, column2 FROM table_name WHERE condition;
```

### Use a common table expression (CTE)
```sql
WITH cte_name AS (
    SELECT * FROM table_name WHERE condition
)
SELECT * FROM cte_name;
```

### Use a window function to calculate a running total
```sql
SELECT column1, column2, SUM(column2) OVER (ORDER BY column1) AS running_total FROM table_name;
```

### Pivot data from rows to columns (e.g., using CASE)
```sql
SELECT
    MAX(CASE WHEN category = 'A' THEN value END) AS A,
    MAX(CASE WHEN category = 'B' THEN value END) AS B
FROM table_name;
```

###  Unpivot data from columns to rows (e.g., using UNION ALL)
```sql
SELECT 'A' AS category, A AS value FROM table_name
UNION ALL
SELECT 'B' AS category, B AS value FROM table_name;
```

### Use recursive CTEs for hierarchical data (e.g., organizational structure)
```sql
WITH RECURSIVE org_hierarchy AS (
    SELECT id, name, manager_id FROM employees WHERE id = start_employee_id
    UNION ALL
    SELECT e.id, e.name, e.manager_id FROM employees e
    INNER JOIN org_hierarchy h ON e.manager_id = h.id
)
SELECT * FROM org_hierarchy;
```

### Use the JSON functions to work with JSON data (e.g., PostgreSQL's JSONB functions)
```sql
SELECT data->>'key' AS value FROM json_table WHERE data->>'key' = 'search_value';
```

### Perform a self-JOIN to find related records (e.g., finding employees who manage other employees)
```sql
SELECT e1.name AS manager, e2.name AS employee
FROM employees e1
INNER JOIN employees e2 ON e1.id = e2.manager_id;
```

### Use the LAG and LEAD window functions to access data from previous and subsequent rows
```sql
SELECT column1, column2, LAG(column2) OVER (ORDER BY column1) AS previous_value, LEAD(column2) OVER (ORDER BY column1) AS next_value
FROM table_name;
```

### Create a stored procedure
```sql
CREATE PROCEDURE procedure_name
AS
BEGIN
    -- SQL statements here
END;
```

### Use a trigger to automatically perform actions on data changes
```sql
CREATE TRIGGER trigger_name
AFTER INSERT ON table_name
FOR EACH ROW
BEGIN
    -- SQL statements here
END;
```

### Perform bulk INSERT operations using the INSERT INTO...VALUES syntax
```sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2), (value3, value4), (value5, value6);
```

### Use the MERGE (or UPSERT) statement to perform INSERT, UPDATE, or DELETE in a single operation (specific syntax may vary by database system)
```sql
MERGE INTO target_table AS target
USING source_table AS source
ON target.id = source.id
WHEN MATCHED THEN
    UPDATE SET target.column1 = source.column1
WHEN NOT MATCHED THEN
    INSERT (column1, column2) VALUES (source.column1, source.column2);
```

### Use the ROLLUP or CUBE clause for multi-dimensional aggregation
```sql
SELECT column1, column2, SUM(value) FROM table_name
GROUP BY ROLLUP (column1, column2);
```

### Calculate the percentile rank of a value in a column
```sql
SELECT column1, column2, PERCENT_RANK() OVER (ORDER BY column2) AS percentile_rank
FROM table_name;
```

### Use window functions to calculate a moving average over a specified window size
```sql
SELECT column1, column2, AVG(column2) OVER (ORDER BY column1 ROWS BETWEEN 2 PRECEDING AND 2 FOLLOWING) AS moving_avg
FROM table_name;
```

### Create and use a user-defined function (UDF)
```sql
CREATE FUNCTION custom_function(param1 datatype, param2 datatype) RETURNS return_datatype AS
BEGIN
    -- SQL statements here
END;
```

### Use the FOR XML clause to generate XML output (SQL Server)
```sql
SELECT column1, column2
FROM table_name
FOR XML AUTO, ROOT('root_element');
```

### Perform a cross-join (Cartesian product) between two tables
```sql
SELECT * FROM table1 CROSS JOIN table2;
```

### Use the HAVING clause with aggregate functions to filter grouped results
```sql
SELECT category, AVG(value) AS avg_value
FROM table_name
GROUP BY category
HAVING AVG(value) > 50;
```











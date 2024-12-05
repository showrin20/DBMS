# DBMS

1. **Note**:.  
   Link: [View File](https://drive.google.com/file/d/1vVsef6lDwAjfm4B81xceGSAKl0rCVX4W/view)  

2. **YouTube Video Links**: 
   Link: [Watch Video](https://youtu.be/jzuzxEFoiss?si=xtAZKA0xM069sfl_)


#SQL

### **Syntax**

**Select**  
Retrieve specific columns from a table.  
```sql
SELECT column1, column2 FROM table_name;
```

**Select Distinct**  
Retrieve unique values of a column.  
```sql
SELECT DISTINCT column_name FROM table_name;
```



### **Filtering**

**Where**  
Filter rows based on a condition.  
```sql
SELECT * FROM table_name WHERE column1 = 'value';
```

**Order By**  
Sort rows in ascending or descending order.  
```sql
SELECT * FROM table_name ORDER BY column1 ASC;
```

**And, Or, Not**  
Combine multiple conditions with logical operators.  
```sql
SELECT * FROM table_name WHERE column1 = 'value1' AND column2 = 'value2';
```



### **Insert, Update, and Delete**

**Insert Into**  
Insert new rows into a table.  
```sql
INSERT INTO table_name (column1, column2) VALUES ('value1', 'value2');
```

**Null Values**  
Check for `NULL` in a column.  
```sql
SELECT * FROM table_name WHERE column1 IS NULL;
```

**Update**  
Modify existing rows in a table.  
```sql
UPDATE table_name SET column1 = 'new_value' WHERE column2 = 'value';
```

**Delete**  
Remove rows from a table.  
```sql
DELETE FROM table_name WHERE column1 = 'value';
```



### **Aggregate Functions**

**Select Top**  
Retrieve the first `N` rows.  
```sql
SELECT TOP 5 * FROM table_name;
```

**Min and Max**  
Get minimum or maximum value of a column.  
```sql
SELECT MIN(column1), MAX(column1) FROM table_name;
```

**Count**  
Count rows or non-NULL values.  
```sql
SELECT COUNT(*) FROM table_name;
```

**Sum**  
Get the total of a numeric column.  
```sql
SELECT SUM(column1) FROM table_name;
```

**Avg**  
Calculate the average of a numeric column.  
```sql
SELECT AVG(column1) FROM table_name;
```



### **Pattern Matching**

**Like**  
Search with a pattern.  
```sql
SELECT * FROM table_name WHERE column1 LIKE 'A%';
```

**Wildcards**  
Use `%` or `_` for flexible matching.  
```sql
SELECT * FROM table_name WHERE column1 LIKE '_a%';
```

**In**  
Match any value in a list.  
```sql
SELECT * FROM table_name WHERE column1 IN ('value1', 'value2');
```

**Between**  
Filter within a range.  
```sql
SELECT * FROM table_name WHERE column1 BETWEEN 10 AND 20;
```



### **Aliases**

**Aliases**  
Rename columns or tables for readability.  
```sql
SELECT column1 AS alias_name FROM table_name AS t;
```



### **Joins**

**Inner Join**  
Match rows in both tables.  
```sql
SELECT * FROM table1 INNER JOIN table2 ON table1.id = table2.id;
```

**Left Join**  
Include all rows from the left table.  
```sql
SELECT * FROM table1 LEFT JOIN table2 ON table1.id = table2.id;
```

**Right Join**  
Include all rows from the right table.  
```sql
SELECT * FROM table1 RIGHT JOIN table2 ON table1.id = table2.id;
```

**Full Join**  
Include all rows when there's a match in either table.  
```sql
SELECT * FROM table1 FULL JOIN table2 ON table1.id = table2.id;
```

**Self Join**  
Join a table to itself.  
```sql
SELECT a.column1, b.column1 FROM table_name a, table_name b WHERE a.id = b.parent_id;
```



### **Combining Queries**

**Union**  
Combine results of multiple queries.  
```sql
SELECT column1 FROM table1 UNION SELECT column1 FROM table2;
```



### **Grouping and Filtering Groups**

**Group By**  
Group rows for aggregate calculations.  
```sql
SELECT column1, COUNT(*) FROM table_name GROUP BY column1;
```

**Having**  
Filter grouped rows.  
```sql
SELECT column1, COUNT(*) FROM table_name GROUP BY column1 HAVING COUNT(*) > 1;
```


### **Existence Checks**

**Exists**  
Check if a subquery returns results.  
```sql
SELECT * FROM table_name WHERE EXISTS (SELECT 1 FROM another_table WHERE column1 = 'value');
```

**Any, All**  
Compare with any or all results of a subquery.  
```sql
SELECT * FROM table_name WHERE column1 > ALL (SELECT column1 FROM another_table);
```



### **Subquery Operations**

**Select Into**  
Create a new table from a query.  
```sql
SELECT * INTO new_table FROM table_name;
```

**Insert Into Select**  
Insert results of a query into a table.  
```sql
INSERT INTO table_name SELECT * FROM another_table;
```



### **Conditional Logic**

**CASE Expression**  
Add conditional logic in queries.  
```sql
SELECT column1, CASE WHEN column2 > 10 THEN 'High' ELSE 'Low' END AS category FROM table_name;
```



### **Null Handling**

**NULL Functions**  
Handle `NULL` values explicitly.  
```sql
SELECT IFNULL(column1, 'default_value') FROM table_name;
```



### **Procedures and Metadata**

**Stored Procedures**  
Reusable SQL code blocks.  
```sql
CREATE PROCEDURE procedure_name AS BEGIN SELECT * FROM table_name; END;
```

**Comments**  
Add comments in queries.  
```sql
-- This is a comment
```



### **Database Management**

**Operators**  
Use arithmetic or comparison operators.  
```sql
SELECT * FROM table_name WHERE column1 + column2 > 10;
```

**Create Database**  
Create a new database.  
```sql
CREATE DATABASE database_name;
```

**Drop Database**  
Delete a database.  
```sql
DROP DATABASE database_name;
```

**Backup Database**  
Backup a database.  
```sql
BACKUP DATABASE database_name TO DISK = 'backup_path';
```



### **Tables and Constraints**

**Create Table**  
Define a new table.  
```sql
CREATE TABLE table_name (id INT PRIMARY KEY, name VARCHAR(50));
```

**Drop Table**  
Delete a table.  
```sql
DROP TABLE table_name;
```

**Alter Table**  
Modify table structure.  
```sql
ALTER TABLE table_name ADD column_name VARCHAR(50);
```

**Constraints**  
Add rules on columns.  
```sql
ALTER TABLE table_name ADD CONSTRAINT unique_constraint UNIQUE (column_name);
```

**Not Null**  
Ensure a column cannot be `NULL`.  
```sql
CREATE TABLE table_name (id INT NOT NULL);
```

**Unique**  
Ensure column values are unique.  
```sql
CREATE TABLE table_name (id INT UNIQUE);
```

**Primary Key**  
Define a column as the primary key.  
```sql
CREATE TABLE table_name (id INT PRIMARY KEY);
```

**Foreign Key**  
Establish a relationship with another table.  
```sql
CREATE TABLE table_name (id INT, FOREIGN KEY (id) REFERENCES another_table(id));
```

**Check**  
Set conditions on column values.  
```sql
CREATE TABLE table_name (age INT CHECK (age >= 18));
```

**Default**  
Set default values for columns.  
```sql
CREATE TABLE table_name (status VARCHAR(10) DEFAULT 'active');
```



### **Indexing and Auto-Increment**

**Create Index**  
Optimize query performance.  
```sql
CREATE INDEX idx_name ON table_name (column1);
```

**Auto Increment**  
Generate sequential values automatically.  
```sql
CREATE TABLE table_name (id INT AUTO_INCREMENT PRIMARY KEY);
```



### **Dates**

**Dates**  
Handle and format date values.  
```sql
SELECT CURRENT_DATE();
```



### **Views**

**View**  
Create a virtual table.  
```sql
CREATE VIEW view_name AS SELECT column1 FROM table_name WHERE column2 = 'value';
```



### **Security and Hosting**

**Injection**  
Prevent SQL injection with parameterized queries.  
```sql
SELECT * FROM table_name WHERE column1 = ?;
```

**Hosting**  
Host a database on a server platform (e.g., AWS, Azure).  



### **Data Types**

**Data Types**  
Define column data types.  
```sql
CREATE TABLE table_name (name VARCHAR(50), age INT);
```

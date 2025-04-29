# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
-- In the Books table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

ISBN             Title                      Author           Publisher   Year
---------------  -------------------------  ---------------  ----------  ----------
978-1234567890   Introduction to AI         John Doe
978-9876543210   Deep Learning              Jane Doe         TechPress   2022
978-1122334455   Cybersecurity Essentials   Alice Smith                  2021

```sql
-- INSERT INTO Books VALUES("978-1234567890","Introduction to AI","John Doe",NULL,NULL);
INSERT INTO Books VALUES("978-9876543210","Deep Learning","Jane Doe","TechPress",2022);
INSERT INTO Books VALUES("978-1122334455","Cybersecurity Essentials","Alice Smith",NULL,2021);

```

**Output:**

![image](https://github.com/user-attachments/assets/a0a1eeee-6c5a-454b-84ae-a1794f51f47a)


**Question 2**
---
-- Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should cascade updates and deletes.
item_desc and rate should not accept NULL.

```sql
Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should cascade updates and deletes.
item_desc and rate should not accept NULL.
```

**Output:**

![image](https://github.com/user-attachments/assets/40ee690a-391d-4850-bec1-34a882f65577)


**Question 3**
---
Insert a book with ISBN 978-1234567890, Title Data Science Essentials, Author Jane Doe, Publisher TechBooks, and Year 2024 into the Books table.

```sql
-- INSERT INTO Books(ISBN, Title, Author, Publisher, Year)
Values('978-1234567890', 'Data Science Essentials', 'Jane Doe', 'TechBooks', 2024)
```

**Output:**

![image](https://github.com/user-attachments/assets/ab1661c5-5a2c-4929-8686-610104527bc7)


**Question 4**
---
-- Insert all products from Discontinued_products into Products.
Table attributes are ProductID, ProductName, Price, Stock

```sql
-- INSERT INTO Products SELECT * FROM Discontinued_products;
```

**Output:**
![image](https://github.com/user-attachments/assets/c523e5ec-33c0-4843-8883-4361d11341ff)

**Question 5**
---
-- Create a table named Orders with the following columns:

OrderID as INTEGER
OrderDate as TEXT
CustomerID as INTEGER

```sql
-- CREATE TABLE Orders(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**

![image](https://github.com/user-attachments/assets/67228173-0f15-4592-8e6a-3bf9ecc5bbe7)


**Question 6**
---
-- Write a SQL Query for inserting the below values in the table Customers

```sql
-- INSERT INTO Customers(ID, NAME, AGE, ADDRESS, SALARY)
VALUES(1, 'Ramesh', 32, 'Ahmedabad', 2000), (2, 'Khilan', 25, 'Delhi', 1500), (3, 'Kaushik', 23, 'Kota', 2000);
```

**Output:**

![image](https://github.com/user-attachments/assets/8cf21631-3a72-4e89-a9bc-7df21ab4cae5)


**Question 7**
---
-- create a table named jobs including columns job_id, job_title, min_salary and max_salary, and make sure that, the default value for job_title is blank and min_salary is 8000 and max_salary is NULL will be entered automatically at the time of insertion if no value assigned for the specified columns.

```sql
-- CREATE TABLE jobs(
job_id INTEGER PRIMARY KEY,
job_title TEXT DEFAULT NULL,
min_salary INTEGER DEFAULT 8000,
max_salary INTEGER DEFAULT NULL
);
```

**Output:**
![image](https://github.com/user-attachments/assets/32e84e68-4351-4390-b53d-ff9182a59d56)


**Question 8**
---
-- Write a SQL query to Add a new column mobilenumber as number in the Student_details table.
Sample table: Student_details

```sql
-- Paste your SQL code below for Question 8
```

**Output:**

ALTER TABLE Student_details ADD mobilenumb number;

**Question 9**
---
-- Create a table named Invoices with the following constraints:
InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
Amount as REAL should be greater than 0.
DueDate as DATE should be greater than the InvoiceDate.
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).
```sql
-- CREATE TABLE Invoices(InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE, Amount REAL CHECK (Amount > 0), 
DueDate DATE CHECK (DueDate > InvoiceDate), 
OrderID INTEGER,
FOREIGN KEY(OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/f0c748d3-3b7b-47fb-b71e-fcff8e13e6ae)


**Question 10**
---
-- Write a SQL query to modify the Student_details table by adding a new column Email of type VARCHAR(50) and updating the column MARKS to have a default value of 0.

```sql
-- ALTER TABLE Student_details ADD COLUMN Email VARCHAR(50);
ALTER TABLE Student_details ADD COLUMN MARKS INT DEFAULT 0;
```

**Output:**
![image](https://github.com/user-attachments/assets/86108c35-a3df-4bb2-8bf8-38f12d6ee88a)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

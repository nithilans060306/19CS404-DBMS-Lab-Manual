# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- Write a SQL statement to Change the supplier name to 'A1 Suppliers' where the supplier ID is 8 in the suppliers table.

```sql
-- UPDATE Suppliers
SET supplier_name = 'A1 Suppliers' 
WHERE supplier_id = 8;
```

**Output:**

![image](https://github.com/user-attachments/assets/08c9cbad-1d25-4fc6-b29a-c0fc6a236996)


**Question 2**
---
-- Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.

```sql
-- UPDATE products
SET product_name = 'Grapefruit'
WHERE product_id = 4;
```

**Output:**

![image](https://github.com/user-attachments/assets/61609fad-afd1-4796-ac19-d71ddd707290)


**Question 3**
---
-- Write a SQL statement to Update the address to '58 Lakeview, Magnolia' where supplier ID is 5 in the suppliers table.

Suppliers Table 

name               type
-----------------  ---------------
supplier_id        INT
supplier_name      VARCHAR(100)
contact_person     VARCHAR(100)
phone_number       VARCHAR(20)
email              VARCHAR(100)
address            VARCHAR(250)

```sql
-- UPDATE Suppliers
SET address = '58 Lakeview, Magnolia'
WHERE supplier_id = 5;
```

**Output:**

![image](https://github.com/user-attachments/assets/ef723575-8579-4bb1-a56b-f57f3e1e74a0)


**Question 4**
---
-- For products with a profit % less than 30% of selling price, update the selling price to provide a profit margin of 35% over cost price of the product in the products table.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT

```sql
-- UPDATE Products
SET sell_price = CAST(cost_price * 1.35 AS INT)
WHERE (sell_price - cost_price) / sell_price * 100 < 30;
```

**Output:**

![image](https://github.com/user-attachments/assets/bd8857f0-8344-4f5f-bf57-02f377719a1e)


**Question 5**
---
-- Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15

```sql
-- UPDATE EMPLOYEES
SET SALARY = SALARY + 500, EMAIL = 'updated'
WHERE JOB_ID = 'SA_REP' AND COMMISSION_PCT > 0.15
```

**Output:**

![image](https://github.com/user-attachments/assets/00b96747-ca97-43f7-9c50-50dca385d9f5)


**Question 6**
---
-- Write a SQL query to Delete customers from 'customer' table where 'GRADE' is less than 2.

```sql
-- DELETE FROM customer WHERE GRADE < 2;
```

**Output:**

![image](https://github.com/user-attachments/assets/af570bdf-8b18-479c-a51a-72a6848efb3b)


**Question 7**
---
-- Write a SQL query to Delete a Specific Surgery whose ID is 3 or surgeon ID is 4.

```sql
-- DELETE FROM surgeries WHERE surgery_id = 3 OR surgeon_id = 4;
```

**Output:**

![image](https://github.com/user-attachments/assets/ff9ebdde-7c15-4fe1-a9a8-75e262f564e5)


**Question 8**
---
-- Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' contains the substring 'Holmes'.

```sql
-- DELETE FROM customer WHERE CUST_NAME LIKE '%holmes%';
```

**Output:**

![image](https://github.com/user-attachments/assets/cd574803-7834-404a-a46c-1c1e292c3dc9)


**Question 9**
---
-- Write a SQL query to Delete customers with 'GRADE' 3 or 'AGENT_CODE' 'A008' whose 'OUTSTANDING_AMT' is less than 5000

```sql
-- DELETE FROM customer WHERE (GRADE = 3 OR AGENT_CODE = 'A008') AND OUTSTANDING_AMT < 5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/946f222f-d237-4e6c-b48a-950e48bac576)

**Question 10**
---
-- Write a SQL query to Delete customers with 'CUST_COUNTRY' 'UK' and 'WORKING_AREA' 'London' whose 'GRADE' is less than 3

```sql
-- DELETE FROM customer WHERE (CUST_COUNTRY = 'UK' AND WORKING_AREA = 'London') AND GRADE < 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/d60efbbd-f068-48be-a744-bc5ac2483e04)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

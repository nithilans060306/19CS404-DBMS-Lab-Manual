# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- What is the total number of appointments scheduled by each doctor?

```sql
-- SELECT DoctorID,  COUNT(DoctorID) as TotalAppointments FROM Appointments GROUP BY DoctorID
```

**Output:**

![image](https://github.com/user-attachments/assets/ae4ed067-8772-447e-9e6a-d46a6b847765)


**Question 2**
---
-- How many male and female doctors are there in each medical specialty?

```sql
-- SELECT Specialty, Gender, COUNT(*) AS TotalDoctors FROM Doctors GROUP BY Specialty, Gender
```

**Output:**

![image](https://github.com/user-attachments/assets/dab9b00b-743e-47f4-b3d7-4a4771722971)


**Question 3**
---
-- How many patients have insurance coverage valid in each year?

Sample table:Insurance Table

name               type
-----------------  ----------
InsuranceID        INTEGER
PatientID          INTEGER
InsuranceCompany   TEXT
PolicyNumber       TEXT
PolicyHolder       TEXT
ValidityPeriod     TEXT
```sql
-- SELECT SUBSTR(ValidityPeriod, 1, 4) AS ValidityYear, Count(*) AS TotalPatients FROM Insurance GROUP BY ValidityYear;
```

**Output:**

![image](https://github.com/user-attachments/assets/6382e891-eb3f-4838-b1e0-38f39105890b)


**Question 4**
---
-- Write a SQL query to count the number of customers. Return number of customers.

Sample table: customer

customer_id |   cust_name    |    city    | grade | salesman_id 

-------------+----------------+------------+-------+-------------

        3002 | Nick Rimando   | New York   |   100 |        5001

        3007 | Brad Davis     | New York   |   200 |        5001

        3005 | Graham Zusi    | California |   200 |        5002

```sql
-- SELECT COUNT(customer_id) AS COUNT FROM customer
```

**Output:**

![image](https://github.com/user-attachments/assets/50591a3a-f775-4b54-b579-27faac8ace0e)


**Question 5**
---
-- Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

```sql
-- SELECT COUNT(id) AS COUNT FROM customer WHERE city <> 'Noida' 
```

**Output:**

![image](https://github.com/user-attachments/assets/7587a454-0b05-425e-92a3-257044cd447b)


**Question 6**
---
-- Write a SQL query to find the minimum purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

 

```sql
-- SELECT MIN(purch_amt) AS MINIMUM FROM orders
```

**Output:**

![image](https://github.com/user-attachments/assets/e6302b55-9d90-4135-a23e-db7a15c8bd04)


**Question 7**
---
-- Write a SQL query to find the total income of employees aged 40 or above.

Table: employee

name        type
----------  ----------
id          INTEGER
name        TEXT
age         INTEGER
city        TEXT
income      INTEGER


```sql
-- SELECT SUM(income) AS total_income FROM employee WHERE age >= 40
```

**Output:**

![image](https://github.com/user-attachments/assets/f2e3391b-6419-4bec-bd92-e142a2cc0d74)


**Question 8**
---
-- Write the SQL query that accomplishes the selection of total number of products for each category from the "products" table, and includes only those products where the minimum category ID is less than 3.

```sql
-- SELECT category_id, count(product_name) FROM products WHERE category_id < 3 GROUP BY category_id 
```

**Output:**

![image](https://github.com/user-attachments/assets/9abd7210-1b22-4d77-81d3-239b8548eed5)


**Question 9**
---
-- Write the SQL query that accomplishes the grouping of data by addresses, calculates the sum of salaries for each address, and excludes addresses where the total salary sum is not greater than 2000.

```sql
-- SELECT address, SUM(salary) FROM customer1 GROUP BY address HAVING SUM(salary) > 2000
```

**Output:**
![image](https://github.com/user-attachments/assets/8d36ebc1-ab20-45c7-8793-2e47ee588229)


**Question 10**
---
-- Write the SQL query that accomplishes the selection of average price for each category from the "products" table and includes only those products where the average price falls between 10 and 15.

```sql
-- SELECT category_id, AVG(Price) FROM products GROUP BY category_id HAVING AVG(Price) BETWEEN 10 AND 15
```

**Output:**

![image](https://github.com/user-attachments/assets/87acf172-e01b-46c9-82e9-0148162566eb)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

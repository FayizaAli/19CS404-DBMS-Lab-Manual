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
 How many patients are covered by each insurance company?

Sample table:Insurance Table

name type

InsuranceID INTEGER PatientID INTEGER InsuranceCompany TEXT PolicyNumber TEXT PolicyHolder TEXT ValidityPeriod TEXT For example:

Result InsuranceCompany TotalPatients

DEF Insurance 1 GHI Insurance 1 GLM Insurance 2 JKL Insurance 1 MNO Insurance 3 PQR Insurance 1 YZA Insurance 1

```sql
select InsuranceCompany, count(PatientID)
as TotalPatients from Insurance group by InsuranceCompany;
```

**Output:**

<img width="1021" height="836" alt="image" src="https://github.com/user-attachments/assets/1a458502-09f1-4ef1-b8a9-789ae3905b31" />


**Question 2**
---
How many appointments are scheduled for each patient?

Sample table: Appointments Table

name type

AppointmentID INTEGER PatientID INTEGER DoctorID INTEGER AppointmentDateTime DATETIME Purpose TEXT Status TEXT For example:

Result PatientID TotalAppointments

3 3 5 2 6 1 7 1 10 3

```sql
select PatientID, count(AppointmentID) as TotalAppointments from Appointments group by PatientID;
```

**Output:**

<img width="1064" height="876" alt="image" src="https://github.com/user-attachments/assets/c7168b8b-5fe3-4f18-9984-1a06fde75121" />


**Question 3**
---
How many medical records are there for each patient?

Sample table:MedicalRecords Table

Result PatientID TotalRecords

4 4 5 1 6 1 7 1 8 1 10 2

```sql
select PatientID, count(RecordID) as TotalRecords from MedicalRecords group by PatientID;
```

**Output:**

<img width="1049" height="884" alt="image" src="https://github.com/user-attachments/assets/fb612f9e-4ee6-47ed-989e-51b6f823b7ac" />


**Question 4**
---
Write a SQL query to calculate the total number of working hours of all employees

Sample table: employee1

For example:

Result Total working hours
111

```sql
select sum(workhour) as "Total working hours" from employee1;
```

**Output:**


<img width="1067" height="468" alt="image" src="https://github.com/user-attachments/assets/a16443d8-23f4-476a-ad79-48324c96e86d" />


**Question 5**
---
Write a SQL query to find the average salary of all employees?

Table: employee

name type

id INTEGER name TEXT age INTEGER city TEXT income INTEGER

For example:

Result Average_Salary
1568750.0

```sql
select avg(income) as "Average_Salary" from employee;
```

**Output:**


<img width="1069" height="492" alt="image" src="https://github.com/user-attachments/assets/12a0ac79-dc26-4d11-8735-8b9c132036f6" />


**Question 6**
---
Write a SQL query to find the total number of unique cities in the customer table?

Table: customer

name type

id INTEGER name TEXT city TEXT email TEXT phone INTEGER For example:

Result unique_cities
10

```sql
select count(distinct city) as unique_cities from customer;
```

**Output:**


<img width="1066" height="489" alt="image" src="https://github.com/user-attachments/assets/0b1a706c-e64a-4367-8b29-1cfe5616f5d9" />


**Question 7**
---
Write a SQL query to calculate the average purchase amount of all orders. Return average purchase amount.

Sample table: orders

ord_no purch_amt ord_date customer_id salesman_id

70001 150.5 2012-10-05 3005 5002

70009 270.65 2012-09-10 3001 5005

70002 65.26 2012-10-05 3002 5001

For example:

Result AVERAGE
1461.765

```sql
select avg(purch_amt) as AVERAGE from orders;
```

**Output:**


<img width="906" height="469" alt="image" src="https://github.com/user-attachments/assets/396153d6-e561-4f99-93f4-4ad5a69d4549" />


**Question 8**
---
Question 8 Write the SQL query that accomplishes the selection of total cost of all products in each category from the "products" table and includes only those products where the total cost is greater than 50.

Sample table: products

For example:

Result category_id Total_Cost

2 63

```sql
select category_id, sum(price) as Total_Cost from products group by category_id having sum(price)>50;
```

**Output:**

<img width="1066" height="519" alt="image" src="https://github.com/user-attachments/assets/5dc2017d-8351-42e5-a1d3-26dcfcf70e6f" />


**Question 9**
---
Write the SQL query that accomplishes the grouping of data by joining date (jdate), calculates the average work hours for each date, and excludes dates where the average work hour is not less than 10.

Sample table: employee1

For example:

Result jdate AVG(workhour)

2002.0 9.5

```sql
select jdate, AVG(workhour) from employee1 group by jdate having AVG(workhour)<10;
```

**Output:**


<img width="1047" height="492" alt="image" src="https://github.com/user-attachments/assets/389961d5-12e3-4d37-9ab7-2b537ec23ebb" />


**Question 10**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the total work hours for each occupation, and excludes occupations where the total work hour sum is not greater than 20.

Sample table: employee1

For example:

Result occupation SUM(workhour)

Business 30 Doctor 30 Engineer 24 Teacher 27

```sql
select occupation, SUM(workhour) from employee1 group by occupation having SUM(workhour)>20;
```

**Output:**


<img width="1074" height="756" alt="image" src="https://github.com/user-attachments/assets/e4414a99-c253-4edb-8eb5-d9df92e7b49c" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

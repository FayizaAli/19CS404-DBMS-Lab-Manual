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
Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE

name type

product_id INT product_name VARCHAR(100) category VARCHAR(50) cost_price DECIMAL(10,2) sell_price DECIMAL(10,2) reorder_lvl INT quantity INT supplier_id INT 
For example:

Test Result select changes(); changes()
4

```sql
update products
set sell_price=round(sell_price*1.10)
where supplier_id=6;
```

**Output:**


<img width="1077" height="790" alt="image" src="https://github.com/user-attachments/assets/3d87968d-f983-43b2-be13-b04f9a2effdb" />


**Question 2**
---
Write a SQL statement to Change the supplier name to 'A1 Suppliers' where the supplier ID is 8 in the suppliers table.

Table info

suppliers(supplier_id,supplier_name,contact_person,phone_number,email,address)

For example:

Test Result select changes(); changes()
1

```sql
update suppliers
set supplier_name='A1 Suppliers'
where supplier_id=8;
```

**Output:**


<img width="1086" height="572" alt="image" src="https://github.com/user-attachments/assets/4bb9371d-2ff9-4554-b81e-ff47ef9b895e" />


**Question 3**
---
Increase the reorder level by 30% for products from 'Food' category having quantity in stock less than 50% of existing reorder level in the products table name type

product_id INT product_name VARCHAR(10) category VARCHAR(50) cost_price DECIMAL(10) sell_price DECIMAL(10) reorder_lvl INT quantity INT supplier_id INT For example:

Test Result select changes(); changes()
4

```sql
update products
set reorder_lvl=round(reorder_lvl*1.30)
where category='Food' and quantity<(reorder_lvl*1.50);
```

**Output:**


<img width="1088" height="588" alt="image" src="https://github.com/user-attachments/assets/6d0bb6d5-fe4e-4542-8e20-2e6cd7c2b8e3" />


**Question 4**
---
Write a SQL statement to change salary of employee to 8000 whose Employee ID is 105, if the existing salary is less than 5000.

Employees table

employee_id first_name last_name email phone_number hire_date job_id salary commission_pct manager_id department_id

```sql
update employees
set salary=8000
where employee_id =105 and salary<5000;
```

**Output:**


<img width="1122" height="433" alt="image" src="https://github.com/user-attachments/assets/f2f723e0-ac61-4174-acdf-a817db23f3ae" />


**Question 5**
---
Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.

products table

product_id product_name category_id availability

```sql
update products
set product_name='Grapefruit'
where product_id=4;
```

**Output:**


<img width="1074" height="399" alt="image" src="https://github.com/user-attachments/assets/b15eeee6-1d0a-4d71-aaf4-fc6b6edb52ec" />


**Question 6**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -

'cust_city' should begin with the letter 'L',
Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
|CUST_CODE | CUST_NAME | CUST_CITY | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO | AGENT_CODE | +-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+ | C00013 | Holmes | London | London | UK | 2 | 6000.00 | 5000.00 | 7000.00 | 4000.00 | BBBBBBB | A003 | | C00001 | Micheal | New York | New York | USA | 2 | 3000.00 | 5000.00 | 2000.00 | 6000.00 | CCCCCCC | A008 | | C00020 | Albert | New York | New York | USA | 3 | 5000.00 |

```sql
delete from customer
where cust_city like 'L%';
```

**Output:**


<img width="1023" height="875" alt="image" src="https://github.com/user-attachments/assets/d223b4ef-18c0-4b6a-a268-b3ccad74be2a" />


**Question 7**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is less than 2.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
|CUST_CODE | CUST_NAME | CUST_CITY | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO | AGENT_CODE | +-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+ | C00013 | Holmes | London | London | UK | 2 | 6000.00 | 5000.00 | 7000.00 | 4000.00 | BBBBBBB | A003 | | C00001 | Micheal | New York | New York | USA | 2 | 3000.00 | 5000.00 | 2000.00 | 6000.00 | CCCCCCC | A008 | | C00020 | Albert | New York | New York | USA | 3 | 5000.00 |

```sql
delete from customer
where grade<2;
```

**Output:**


<img width="1060" height="771" alt="image" src="https://github.com/user-attachments/assets/cb563d34-d283-4bbe-931a-7919a9cd8947" />


**Question 8**
---
Write a SQL query to Delete customers from 'customer' table where 'AGENT_CODE' is either 'A003' or 'A008'.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
|CUST_CODE | CUST_NAME | CUST_CITY | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO | AGENT_CODE | +-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+ | C00013 | Holmes | London | London | UK | 2 | 6000.00 | 5000.00 | 7000.00 | 4000.00 | BBBBBBB | A003 | | C00001 | Micheal | New York | New York | USA | 2 | 3000.00 | 5000.00 | 2000.00 | 6000.00 | CCCCCCC | A008 | | C00020 | Albert | New York | New York | USA | 3 | 5000.00 |

```sql
delete from customer
where AGENT_CODE in ('A003','A008');
```

**Output:**

<img width="1047" height="906" alt="image" src="https://github.com/user-attachments/assets/0f2a46a2-570b-499d-bf61-1192eb0b463f" />


**Question 9**
---
Write a SQL query to Delete customers from 'customer' table where 'WORKING_AREA' is 'New York'.

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
|CUST_CODE | CUST_NAME | CUST_CITY | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO | AGENT_CODE | +-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+ | C00013 | Holmes | London | London | UK | 2 | 6000.00 | 5000.00 | 7000.00 | 4000.00 | BBBBBBB | A003 | | C00001 | Micheal | New York | New York | USA | 2 | 3000.00 | 5000.00 | 2000.00 | 6000.00 | CCCCCCC | A008 | | C00020 | Albert | New York | New York | USA | 3 | 5000.00 |

```sql
delete from customer
where working_area='New York';
```

**Output:**


<img width="1036" height="860" alt="image" src="https://github.com/user-attachments/assets/716b8dfc-be51-435b-b400-8d0595ea717f" />


**Question 10**
---
Write a SQL query to Delete customers with 'CUST_COUNTRY' 'UK' and 'WORKING_AREA' 'London' whose 'GRADE' is less than 3

Sample table: Customer

+-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+
|CUST_CODE | CUST_NAME | CUST_CITY | WORKING_AREA | CUST_COUNTRY | GRADE | OPENING_AMT | RECEIVE_AMT | PAYMENT_AMT |OUTSTANDING_AMT| PHONE_NO | AGENT_CODE | +-----------+-------------+-------------+--------------+--------------+-------+-------------+-------------+-------------+---------------+--------------+------------+ | C00013 | Holmes | London | London | UK | 2 | 6000.00 | 5000.00 | 7000.00 | 4000.00 | BBBBBBB | A003 | | C00001 | Micheal | New York | New York | USA | 2 | 3000.00 | 5000.00 | 2000.00 | 6000.00 | CCCCCCC | A008 | | C00020 | Albert | New York | New York | USA | 3 | 5000.00 | 7000.00 | 6000.00 | 6000.00 | BBBBSBB | A008 | For example:

Test Result select changes(); changes()
4

```sql
delete from customer
where cust_country='UK' and
working_area='London' and
grade<3;
```

**Output:**


<img width="1043" height="678" alt="image" src="https://github.com/user-attachments/assets/8450a9f5-453d-47c5-b435-52afe141b63a" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

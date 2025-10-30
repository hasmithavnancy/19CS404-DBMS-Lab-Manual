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

<img width="754" height="360" alt="image" src="https://github.com/user-attachments/assets/9b569620-23a9-4d99-a976-9ea566246c31" />

```sql
UPDATE Employees
SET 
    salary = salary + 500,
    email = 'updated'
WHERE 
    job_id = 'SA_REP'
    AND commission_pct > 0.15;
```

**Output:**

<img width="983" height="302" alt="image" src="https://github.com/user-attachments/assets/f4e39acc-7429-41ae-b9ea-effbba1e1db9" />


**Question 2**

<img width="768" height="168" alt="image" src="https://github.com/user-attachments/assets/ef7c16a3-7569-48eb-ae01-4ad062034cb5" />

```sql
UPDATE suppliers
SET supplier_name = 'A1 Suppliers'
WHERE supplier_id = 8;
```

**Output:**

<img width="1190" height="249" alt="image" src="https://github.com/user-attachments/assets/77a68a76-8f28-43ee-bd22-5780a4c6787a" />

**Question 3**

<img width="631" height="166" alt="image" src="https://github.com/user-attachments/assets/b835fb3a-6a58-48a9-9016-d763ceb499af" />

```sql
UPDATE Products
SET 
    sell_price = sell_price * 1.10
WHERE 
    category = 'Bakery';
```

**Output:**

<img width="1280" height="300" alt="image" src="https://github.com/user-attachments/assets/45f99369-fcda-48ee-8363-91046ac5bbfd" />

**Question 4**

<img width="578" height="167" alt="image" src="https://github.com/user-attachments/assets/e2a0ec80-743e-4837-a3bc-e3f938339df5" />

```sql
UPDATE Products
SET 
    quantity = quantity * 1.10;
```

**Output:**

<img width="1114" height="357" alt="image" src="https://github.com/user-attachments/assets/f9e87bd4-bd23-42fd-a837-f8a3235de44b" />


**Question 5**

<img width="704" height="286" alt="image" src="https://github.com/user-attachments/assets/4ef193e5-44b0-4d7b-8d4a-287fe1040e8d" />


```sql
UPDATE Products
SET category = 'Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

<img width="1311" height="292" alt="image" src="https://github.com/user-attachments/assets/3e96ec19-e017-4c15-9bc0-6427a46a6d92" />


**Question 6**

<img width="664" height="259" alt="image" src="https://github.com/user-attachments/assets/4bf249b1-ed36-41b2-898e-a2d662c8b851" />


```sql
DELETE FROM Surgeries
WHERE surgery_date = '2024-02-28';
```

**Output:**

<img width="806" height="237" alt="image" src="https://github.com/user-attachments/assets/d5777352-1254-4c97-aee3-398848b2ceae" />


**Question 7**

<img width="884" height="246" alt="image" src="https://github.com/user-attachments/assets/0036fedc-2653-4a7c-98e0-2e3b21ad6931" />


```sql
DELETE FROM Customer
WHERE (GRADE = 3 OR AGENT_CODE = 'A008')
  AND OUTSTANDING_AMT < 5000;
```

**Output:**

<img width="1067" height="169" alt="image" src="https://github.com/user-attachments/assets/f839beca-1414-43d6-88d5-001557a818f8" />


**Question 8**

<img width="909" height="80" alt="image" src="https://github.com/user-attachments/assets/a79a997a-abbd-48f1-9758-782688072985" />


```sql
DELETE FROM Doctors
WHERE specialization = 'Cardiology';
```

**Output:**

<img width="843" height="242" alt="image" src="https://github.com/user-attachments/assets/9c3e631a-47f4-4de8-9747-d0a57e1f04f8" />


**Question 9**

<img width="868" height="267" alt="image" src="https://github.com/user-attachments/assets/0b0de177-86c6-449d-a057-af0e7367e48e" />


```sql
DELETE FROM Doctors
WHERE (specialization = 'Pediatrics' OR specialization = 'Cardiology')
  AND last_name = 'Brown';
```

**Output:**

<img width="731" height="531" alt="image" src="https://github.com/user-attachments/assets/9dd7d550-2e93-4154-afd7-57a44e31d6e5" />


**Question 10**
<img width="963" height="235" alt="image" src="https://github.com/user-attachments/assets/d872652b-3874-40cb-ae97-88d8fa577600" />


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY = 'UK'
  AND WORKING_AREA = 'London'
  AND GRADE < 3;
```

**Output:**

<img width="1051" height="188" alt="image" src="https://github.com/user-attachments/assets/754e1d30-4f0f-4bb1-90d1-13edee701eff" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.





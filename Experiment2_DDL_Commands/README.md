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
<img width="924" height="368" alt="image" src="https://github.com/user-attachments/assets/5cd0c32b-2916-4821-85a8-7c82ab50127d" />

```sql
INSERT INTO Employee (EmployeeID, Name, Position, Department, Salary)
VALUES
(2, 'John Smith', 'Developer', 'IT', 75000),
(3, 'Anna Bell', 'Designer', 'Marketing', 68000);
```

**Output:**

<img width="1281" height="288" alt="image" src="https://github.com/user-attachments/assets/4d19c18a-e820-49cb-9f50-f709328bc128" />


**Question 2**
---
<img width="1018" height="240" alt="image" src="https://github.com/user-attachments/assets/3c40c839-aba5-45e9-94e6-9973751019ec" />


```sql
CREATE TABLE Products(
ProductID  INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK (Price>0),
StockQuantity INTEGER CHECK (StockQuantity >= 0)
);
```

**Output:**

<img width="1293" height="179" alt="image" src="https://github.com/user-attachments/assets/07f989e9-9a83-4897-bfa8-c8f5bd2e78bc" />


**Question 3**
---
<img width="1129" height="207" alt="image" src="https://github.com/user-attachments/assets/a5019673-f2be-4ca9-9e3b-9bf5cf6e2c59" />


```sql
CREATE TABLE contacts
(
contact_id  INTEGER PRIMARY KEY,
first_name TEXT NOT NULL,
last_name TEXT NOT NULL,
email TEXT,
phone TEXT NOT NULL,
CHECK (LENGTH(phone)>=10)
);
```

**Output:**

<img width="1380" height="193" alt="image" src="https://github.com/user-attachments/assets/04e99352-1363-43ac-a2e3-dad741e20ef4" />


**Question 4**
---
<img width="654" height="165" alt="image" src="https://github.com/user-attachments/assets/6c4fcd0d-ffef-44a5-9789-20976dea52a9" />


```sql
ALTER TABLE Customers
ADD COLUMN email TEXT;
```

**Output:**

<img width="978" height="177" alt="image" src="https://github.com/user-attachments/assets/93089928-1523-4386-ab43-d59ed45f7f25" />


**Question 5**
---
<img width="778" height="171" alt="image" src="https://github.com/user-attachments/assets/494af078-e062-469d-bd7a-99a56a960666" />


```sql
CREATE TABLE Shipments (
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY (SupplierID) REFERENCES 
Suppliers(SupplierID),
FOREIGN KEY (OrderID) REFERENCES 
Orders(OrderID)
);
```

**Output:**

<img width="937" height="159" alt="image" src="https://github.com/user-attachments/assets/32ed4c6a-465c-4518-a7d4-fa5451173431" />


**Question 6**
---
<img width="691" height="113" alt="image" src="https://github.com/user-attachments/assets/172a37fa-b551-4548-9068-b1d6defdcec0" />


```sql
INSERT INTO Products (ProductID, Name, Category)
VALUES (104, 'Tablet','Electronics');
```

**Output:**

<img width="847" height="154" alt="image" src="https://github.com/user-attachments/assets/90818ddc-8720-429b-9ef1-a56978f60d2e" />


**Question 7**
---
<img width="597" height="231" alt="image" src="https://github.com/user-attachments/assets/d4461dbf-68e2-4454-9bb4-f6fc4111283a" />


```sql
CREATE TABLE Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT
);
```

**Output:**

<img width="1004" height="226" alt="image" src="https://github.com/user-attachments/assets/0a627359-5f14-473c-ab06-312e6a931afd" />


**Question 8**
---


```sql
INSERT INTO Employee (EmployeeID, Name, Department, Salary)
SELECT EmployeeID, Name, Department, Salary
FROM Former_employees;
```

**Output:**

<img width="539" height="205" alt="image" src="https://github.com/user-attachments/assets/2b3b9006-72c1-44e9-bb09-95f970c6354e" />


**Question 9**
---


```sql
ALTER TABLE employee
RENAME COLUMN id TO employee_id;
```

**Output:**

<img width="889" height="169" alt="image" src="https://github.com/user-attachments/assets/57018db4-8b4d-48a7-a196-eb7b97a8d0c0" />


**Question 10**
---
<img width="756" height="168" alt="image" src="https://github.com/user-attachments/assets/0fd6367c-702f-41aa-8fc6-c8751e9a0684" />


```sql
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER,
FOREIGN KEY (CustomerID) REFERENCES 
Customers(CustomerID)
);
```

**Output:**

<img width="974" height="184" alt="image" src="https://github.com/user-attachments/assets/080d4f66-da8c-435b-bfdb-6ad3783b99b8" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

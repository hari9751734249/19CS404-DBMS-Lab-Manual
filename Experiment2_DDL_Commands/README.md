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
<img width="634" height="351" alt="image" src="https://github.com/user-attachments/assets/f47c2cf8-eaf4-418f-895f-468ba215f693" />

sql 
```
insert into Employee(EmployeeID, Name, Position,Department, Salary)
values(5, 'George Clark', 'Consultant', null, null),
(7, 'Noah Davis', 'Manager', 'HR',60000),
(8, 'Ava Miller','Consultant','IT',null);
```

**Output:**

<img width="458" height="209" alt="image" src="https://github.com/user-attachments/assets/36ed5ae9-f931-4cc3-b0b2-b0e26d6896ad" />


**Question 2**
---
<img width="636" height="221" alt="image" src="https://github.com/user-attachments/assets/12496a27-c9ac-46af-a5d1-8c223a38ca8e" />

sql
```
insert into Products(ProductID, Name, Category, Price, Stock)
values(101, 'Laptop','Electronics',1500, 50);
```

**Output:**
<img width="721" height="251" alt="image" src="https://github.com/user-attachments/assets/2b22653f-fc68-46cf-b55f-bef97a281977" />


**Question 3**
---
<img width="719" height="395" alt="image" src="https://github.com/user-attachments/assets/9332a66a-f9cb-4884-9698-9bc3ba456e49" />

sql
```
create table Attendance(
AttendanceID INTEGER primary key,
EmployeeID INTEGER references Employees(EmployeeID),
AttendanceDate DATE,
Status TEXT check(status in( 'Present', 'Absent', 'Leave'))

):
```

**Output:**

<img width="806" height="436" alt="image" src="https://github.com/user-attachments/assets/8379378f-9410-43c3-858b-6d28ffce107e" />


**Question 4**
---
<img width="803" height="439" alt="image" src="https://github.com/user-attachments/assets/12ef1d1b-ce02-4518-8101-24b810dc7c1e" />

sql
```




create table Shipments(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER references Suppliers(SupplierID),
OrderID INTEGER references Orders(OrderID)
);
```

**Output:**

<img width="804" height="389" alt="image" src="https://github.com/user-attachments/assets/708d089f-552d-49cc-b9dc-93abdc56dd88" />


**Question 5**
---
<img width="808" height="430" alt="image" src="https://github.com/user-attachments/assets/ed9a9b48-0f41-4fe7-a0df-2936ba920203" />

sql
```
insert into Customers(CustomerID, Name, Address, Email)
select CustomerID, Name, Address, Email
from Old_customers;
```

**Output:**

<img width="803" height="435" alt="image" src="https://github.com/user-attachments/assets/ed93a7a5-f935-4c83-b9bf-00e51d52bba8" />


**Question 6**
---
<img width="803" height="425" alt="image" src="https://github.com/user-attachments/assets/fe4d8016-7f77-46e1-90f9-2fa7dd6e6464" />

sql
```
create table Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE,
DueDate DATE check (DueDate>InvoiceDate),
Amount REAL check (Amount >0)

);
```

**Output:**

<img width="806" height="425" alt="image" src="https://github.com/user-attachments/assets/195669e7-3cfa-46cf-98a7-f33a4f65fc95" />



**Question 7**
---
 <img width="805" height="430" alt="image" src="https://github.com/user-attachments/assets/06fcc182-2949-495f-88bd-662c8ac8e495" />

sql
```
create table Orders(
OrderID INTEGER primary key,
OrderDate DATE not NULL,
CustomerID INTEGER references Customers(CustomerID)

);
```

**Output:**

<img width="803" height="437" alt="image" src="https://github.com/user-attachments/assets/47f6d6aa-34e6-4c87-bb08-bc4ce341ad3e" />


**Question 8**
---
<img width="805" height="392" alt="image" src="https://github.com/user-attachments/assets/1e08aafd-1f30-4d59-b36c-e65a6f52d88c" />

sql
```
alter table employee add column first_name varchar(50);
alter table employee add column last_name varchar(50);
```

**Output:**

<img width="806" height="437" alt="image" src="https://github.com/user-attachments/assets/8d4f6a0d-9619-4dc5-a749-70b536b07763" />



**Question 9**
<img width="803" height="330" alt="image" src="https://github.com/user-attachments/assets/a351fb5a-aca9-4e13-b012-046c5a7327da" />

sql
```
alter table Student_details add column Email VARCHAR(50);
alter table Student_details add column MARKS default 0;
```

**Output:**

<img width="805" height="407" alt="image" src="https://github.com/user-attachments/assets/c6b8132e-0db8-4fe4-a3b9-c004cda37a97" />


**Question 10**
---
<img width="803" height="410" alt="image" src="https://github.com/user-attachments/assets/2683c950-7102-4a13-84c9-c1fc5b115f1c" />

sql
```
create table Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT

);
```

**Output:**

<img width="577" height="410" alt="image" src="https://github.com/user-attachments/assets/eddb9e52-2741-4fac-a7ec-194f64b56dd9" />

**Grades**

<img width="719" height="331" alt="image" src="https://github.com/user-attachments/assets/3fbfb117-8ecb-41d9-81c1-23c209a553d8" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

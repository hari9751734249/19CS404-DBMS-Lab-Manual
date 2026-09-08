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
<img width="689" height="328" alt="image" src="https://github.com/user-attachments/assets/d9d19bf1-596b-4f6a-9c54-f3c7375117e5" />

sql
```
Update   suppliers 
set address = '58 Lakeview, Magnolia' 
where supplier_id = 5;
```

**Output:**
<img width="647" height="326" alt="image" src="https://github.com/user-attachments/assets/49b26791-6dcb-4f49-a713-86a1e999b82a" />


**Question 2**
---
<img width="700" height="263" alt="image" src="https://github.com/user-attachments/assets/7d49c3af-22a1-45cd-93e9-8e123f816cb4" />

sql
```
Update products 
set product_name ='Premium Bread' 
where product_id = 5;  
```

**Output:**

<img width="625" height="309" alt="image" src="https://github.com/user-attachments/assets/16fd4de8-a685-4a71-870b-7552b386e6b4" />


**Question 3**
---
<img width="692" height="410" alt="image" src="https://github.com/user-attachments/assets/c583d87d-6f56-4f89-9957-a31ee96635b8" />

sql
```
update products 
set reorder_lvl =reorder_lvl*0.7
where cost_price >50 and quantity  <100;
```

**Output:**
<img width="611" height="344" alt="image" src="https://github.com/user-attachments/assets/2c14de7a-867b-4a31-8de2-2f24380519d4" />


**Question 4**
---
<img width="714" height="326" alt="image" src="https://github.com/user-attachments/assets/64edabb4-9647-4a51-b729-0651aba1d091" />

sql
```
update suppliers 
set  supplier_name=upper( supplier_name)
where contact_person like '%Singh%'; 
```

**Output:**
<img width="593" height="290" alt="image" src="https://github.com/user-attachments/assets/4e79909b-4f03-4aee-90c6-a89b4edd769b" />


**Question 5**
---
<img width="630" height="181" alt="image" src="https://github.com/user-attachments/assets/610991f9-4db1-4a8f-bdd3-993fc9a29569" />

sql
```
update products 
set availability = availability*2
where product_id= 1;
```

**Output:**

<img width="614" height="220" alt="image" src="https://github.com/user-attachments/assets/895c1e06-7b8a-4099-89a6-c82f8e93b71b" />


**Question 6**
---
<img width="690" height="353" alt="image" src="https://github.com/user-attachments/assets/344a87a4-6156-48ed-994f-8311d453766a" />

sql
```
delete from customer 
where CUST_COUNTRY not in ('India','USA'); 
```

**Output:**
<img width="606" height="405" alt="image" src="https://github.com/user-attachments/assets/8d057330-b2fe-4323-9433-7b1c9699a60a" />


**Question 7**
---
<img width="737" height="458" alt="image" src="https://github.com/user-attachments/assets/f1aacd0a-e23b-41ec-813b-69b691805d25" />

sql
```
delete from customer
where cust_country ='India'and cust_city!='Chennai'; 
```

**Output:**

<img width="648" height="443" alt="image" src="https://github.com/user-attachments/assets/ff87d3c7-0669-402f-99ce-5951b6bd4962" />


**Question 8**
---
<img width="684" height="392" alt="image" src="https://github.com/user-attachments/assets/bd38c716-ac19-4b1b-8404-6d49ebdb43e7" />

sql
```
delete from doctors
where   specialization  is null;
```

**Output:**

<img width="605" height="443" alt="image" src="https://github.com/user-attachments/assets/31806630-dd4f-4fbc-88ee-6c4566618769" />


**Question 9**
---
<img width="709" height="172" alt="image" src="https://github.com/user-attachments/assets/5bd9f2d7-786e-4510-a38a-a2c6d74b6115" />

sql
```
delete from doctors
where Specialization  ='Pediatrics' and first_name = 'Michael'; 
```

**Output:**
<img width="640" height="295" alt="image" src="https://github.com/user-attachments/assets/36865b02-2a47-4498-8d21-d3f3b27f9396" />



**Question 10**
---
<img width="731" height="446" alt="image" src="https://github.com/user-attachments/assets/350eee1c-b51a-498d-8dca-8afb0d024d50" />


sql
```
delete from customer
where grade >=2;
```

**Output:**

<img width="572" height="407" alt="image" src="https://github.com/user-attachments/assets/ca7217cb-19be-483f-aee5-4e3b0bb05560" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

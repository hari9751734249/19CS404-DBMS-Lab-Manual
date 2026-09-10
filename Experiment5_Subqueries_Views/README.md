# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--

<img width="732" height="443" alt="image" src="https://github.com/user-attachments/assets/7300ecff-5a06-4070-bf8b-a87cb325e86a" />

sql
```
select *
from CUSTOMERS
where salary >1500;
```

**Output:**


<img width="647" height="440" alt="image" src="https://github.com/user-attachments/assets/aa66d29f-8ea2-45cd-bf1c-211b2aebfe6f" />


**Question 2**
---

<img width="693" height="446" alt="image" src="https://github.com/user-attachments/assets/1f1316d1-0949-438a-bbbe-434ed9ae3300" />

sql
```
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id in(
select salesman_id
from salesman
where city = 'New York');

```

**Output:**


<img width="652" height="347" alt="image" src="https://github.com/user-attachments/assets/b809fede-471d-4b47-b724-14225b8db897" />



**Question 3**
---


<img width="710" height="449" alt="image" src="https://github.com/user-attachments/assets/f5dfd220-1e31-484f-8716-767a0a9d41c8" />

sql
```
select * from employee
where age<(
select avg(age)
from employee
where income > 250000);
```

**Output:**


<img width="646" height="387" alt="image" src="https://github.com/user-attachments/assets/e7acf46d-a26c-426d-baef-874380c9a164" />



**Question 4**
---


<img width="710" height="435" alt="image" src="https://github.com/user-attachments/assets/776c94ac-326a-4960-9f9c-0aee0fa25b76" />

sql
```
select student_name,grade
from GRADES g1
where grade =(
select min(grade)
from GRADES g2
where g2.subject=g1.subject);
```

**Output:**


<img width="485" height="321" alt="image" src="https://github.com/user-attachments/assets/ccb47701-2163-4792-8da8-ed34c9b10741" />


**Question 5**
---
<img width="690" height="446" alt="image" src="https://github.com/user-attachments/assets/57b9d6f0-51db-4180-be6e-1afa78f26ef3" />

sql
```
select * from CUSTOMERS  where AGE<30;
```

**Output:**


<img width="646" height="420" alt="image" src="https://github.com/user-attachments/assets/31fff8b1-ea8a-4c3e-8acc-28456595c865" />


**Question 6**
---


<img width="704" height="341" alt="image" src="https://github.com/user-attachments/assets/4803dead-1a32-4625-969b-ca1b93708742" />

sql
```
select  department_id, department_name
from Departments
where length( department_name)>(select avg(length( department_name))
from Departments  );
```

**Output:**


<img width="445" height="309" alt="image" src="https://github.com/user-attachments/assets/61fb0387-5e31-45c2-80b2-ad0b0f927a8d" />



**Question 7**
---


<img width="719" height="437" alt="image" src="https://github.com/user-attachments/assets/21c24fc4-22bd-4696-b83b-88501ab58f04" />

sql
```
select ord_no, purch_amt, ord_date, customer_id, salesman_id
from orders
where salesman_id in (
select salesman_id
from salesman
where city = 'London'
);
```

**Output:**


<img width="651" height="338" alt="image" src="https://github.com/user-attachments/assets/b3ab7f4a-9ff1-4899-a06d-7889f2e1661e" />


**Question 8**
---


<img width="643" height="403" alt="image" src="https://github.com/user-attachments/assets/80ff7b79-002c-4bf8-8039-d40cbeeca9e3" />

sql
```
select medication_id, medication_name,dosage
from Medications
where dosage =(select max(dosage) from Medications  );
```

**Output:**


<img width="635" height="336" alt="image" src="https://github.com/user-attachments/assets/abb16c80-f93c-49d5-8968-d3b6c951fd69" />


**Question 9**
---


<img width="716" height="410" alt="image" src="https://github.com/user-attachments/assets/5af9dfc4-f71f-4ce5-a021-3204ce56cd3d" />

sql
```
select  student_name,  grade 
from GRADES g1
where grade=(
select max(grade)
from GRADES g2
where g2.subject=g1.subject
);
```

**Output:**


<img width="531" height="335" alt="image" src="https://github.com/user-attachments/assets/df38e252-caf3-4bc3-b1e4-fc98da0542df" />


**Question 10**
---


<img width="722" height="439" alt="image" src="https://github.com/user-attachments/assets/11b002e0-9b91-4e25-afcc-7250deeacee3" />

sql
```
select ord_no, purch_amt, ord_date, customer_id,salesman_id
from orders
where salesman_id =(
select salesman_id
from salesman
where name='Paul Adam' 
);
```

**Output:**



<img width="660" height="337" alt="image" src="https://github.com/user-attachments/assets/d14c8eda-eb17-4e17-8e3c-2b02e79d1eff" />

**GRADES**


<img width="610" height="183" alt="image" src="https://github.com/user-attachments/assets/972365cb-5d95-4e7a-b159-bb4f80876471" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.

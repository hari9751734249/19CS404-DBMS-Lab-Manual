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
<img width="677" height="444" alt="image" src="https://github.com/user-attachments/assets/5b12b4b3-4a52-41ba-bd17-5e3487beb554" />

sql
```
select InsuranceCompany , avg(EndDate-StartDate) as AvgCoverageDurationDays 
from Insurance 
group by InsuranceCompany;
```

**Output:**

<img width="602" height="438" alt="image" src="https://github.com/user-attachments/assets/506b97eb-cf1e-45b2-a118-8ee21818c66d" />

**Question 2**
---
<img width="736" height="436" alt="image" src="https://github.com/user-attachments/assets/01b6f5a0-0f88-4464-a71a-da8e2b76bee6" />

sql
```
select DoctorID , count(*) as TotalPrescriptions 
from Prescriptions 
group by DoctorID;
```

**Output:**

<img width="611" height="457" alt="image" src="https://github.com/user-attachments/assets/c6d9fc37-c803-4572-96b2-1d0768c7bc16" />


**Question 3**
---
<img width="711" height="402" alt="image" src="https://github.com/user-attachments/assets/c2c083dc-129a-4276-a1a4-5bf321ea889c" />

sql
```
SELECT
Specialty,
Gender,
COUNT(DoctorId) AS TotalDoctors
FROM Doctors
GROUP BY Specialty,Gender;
```

**Output:**
<img width="614" height="446" alt="image" src="https://github.com/user-attachments/assets/a856112e-3e47-431a-948c-330579127673" />



**Question 4**
---
<img width="675" height="371" alt="image" src="https://github.com/user-attachments/assets/bcbbd4b3-59fd-4204-a373-d5e75773f1b4" />

sql
```
SELECT
MAX(purch_amt) AS MAXIMUM
FROM orders;
```

**Output:**
<img width="329" height="259" alt="image" src="https://github.com/user-attachments/assets/b160626b-3aff-4afa-a09d-3abd486facad" />



**Question 5**
---
<img width="735" height="358" alt="image" src="https://github.com/user-attachments/assets/5233c2be-109c-492a-94fe-2a04267ed778" />

sql
```
SELECT
COUNT(DISTINCT age) "COUNT"
FROM employee;
```

**Output:**
<img width="308" height="286" alt="image" src="https://github.com/user-attachments/assets/9fe7640c-84cf-4665-b2c6-e2f8424ae2aa" />


**Question 6**
---
<img width="636" height="349" alt="image" src="https://github.com/user-attachments/assets/1571e855-b08b-4a72-a805-f5f34a46e43b" />

sql
```
SELECT
COUNT(id) AS employees_count
FROM employee
WHERE income>50;
```

**Output:**

<img width="416" height="286" alt="image" src="https://github.com/user-attachments/assets/b22d7f7c-775c-465d-9e6e-e65dc19a8176" />


**Question 7**
---
<img width="623" height="339" alt="image" src="https://github.com/user-attachments/assets/2c3de250-3766-48ce-b523-4bb4ba9f809b" />

sql
```
SELECT
COUNT(DISTINCT city) AS unique_cities
FROM customer;
```

**Output:**
<img width="322" height="264" alt="image" src="https://github.com/user-attachments/assets/443e6af0-5516-4da6-a9a5-253ca193a64c" />



**Question 8**
---
<img width="716" height="406" alt="image" src="https://github.com/user-attachments/assets/999dbb1a-2c4d-4db8-94cb-096084a8d675" />

sql
```
SELECT
category_id,
SUM(price*category_id) AS Revenue
FROM products
GROUP BY category_id
HAVING Revenue>25;
```

**Output:**

<img width="416" height="337" alt="image" src="https://github.com/user-attachments/assets/1e53663e-729e-440a-ad7d-0092d0a7cb47" />


**Question 9**
---
<img width="686" height="371" alt="image" src="https://github.com/user-attachments/assets/f69c0449-9c43-4e3a-8783-a699a6d6f92f" />

sql
```
SELECT
age,
MAX(income)
FROM employee
GROUP BY age
HAVING income>2000000;
```

**Output:**
<img width="414" height="301" alt="image" src="https://github.com/user-attachments/assets/57d522f5-efe1-4460-a893-58640e00b618" />


**Question 10**
---
<img width="608" height="391" alt="image" src="https://github.com/user-attachments/assets/06ffa5cb-2e22-42ed-9e6f-5bff1a45bfb2" />

sql
```
SELECT
PatientID,
COUNT(PatientID) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID
HAVING COUNT(RecordID)>3;
```

**Output:**

<img width="473" height="323" alt="image" src="https://github.com/user-attachments/assets/cc5d4dd7-1be0-41b4-b1ee-28c6902c3144" />

## GRADE
<img width="656" height="167" alt="image" src="https://github.com/user-attachments/assets/87a7de65-9c99-42b6-8494-5afb06d5dc90" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

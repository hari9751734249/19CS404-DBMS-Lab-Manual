# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--


<img width="727" height="407" alt="image" src="https://github.com/user-attachments/assets/b1af749f-5e54-4a6e-9b5d-9c5f7dcd0181" />

sql
```
SELECT 
    salesman.name AS Salesman,
    customer.cust_name,
    salesman.city
FROM salesman
JOIN customer
ON salesman.city = customer.city;
```

**Output:**


<img width="663" height="415" alt="image" src="https://github.com/user-attachments/assets/41b7be1e-a915-40c6-b291-f906c078d899" />


**Question 2**
---


<img width="731" height="416" alt="image" src="https://github.com/user-attachments/assets/c6375864-1569-4281-a907-c8e20d0a0fc3" />

sql
```
SELECT p.*
FROM patients AS p
INNER JOIN appointments AS a
    ON p.patient_id = a.patient_id
WHERE a.appointment_date BETWEEN '2024-02-01' AND '2024-02-28';
```

**Output:**


<img width="641" height="349" alt="image" src="https://github.com/user-attachments/assets/bdc508e3-2298-4a94-a061-e15170415de3" />


**Question 3**
---


<img width="712" height="400" alt="image" src="https://github.com/user-attachments/assets/5efc3820-adb7-4bf8-aac0-977cc7f5053a" />

sql
```
SELECT 
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS Salesman,
    s.commission
FROM customer AS c
INNER JOIN salesman AS s
    ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;
```

**Output:**


<img width="608" height="401" alt="image" src="https://github.com/user-attachments/assets/d2b643dd-42fa-4042-b532-c5032254d82a" />


**Question 4**
---


<img width="722" height="398" alt="image" src="https://github.com/user-attachments/assets/b02a440a-858f-4a50-a447-12e4951391b3" />

sql
```
SELECT 
    s.name AS salesman_name,
    c.cust_name AS customer_name
FROM salesman AS s
LEFT JOIN customer AS c
    ON s.salesman_id = c.salesman_id;
```

**Output:**


<img width="485" height="406" alt="image" src="https://github.com/user-attachments/assets/b54aae68-ee19-406a-bcde-dcd389eb8a5c" />


**Question 5**
---
<img width="687" height="413" alt="image" src="https://github.com/user-attachments/assets/b21e03d8-114d-4d83-aafd-bb4c0551f4c0" />

sql
```
SELECT
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders AS o
INNER JOIN customer AS c
    ON o.customer_id = c.customer_id
INNER JOIN salesman AS s
    ON o.salesman_id = s.salesman_id;
```

**Output:**


<img width="615" height="413" alt="image" src="https://github.com/user-attachments/assets/e69160f3-c9df-459f-aaac-551145ef500d" />



**Question 6**
---

<img width="683" height="404" alt="image" src="https://github.com/user-attachments/assets/e62f3826-91f3-4740-b7fe-965c33350479" />


sql
```
SELECT c.cust_name
FROM customer AS c
LEFT JOIN orders AS o
    ON c.customer_id = o.customer_id;
```

**Output:**

<img width="286" height="413" alt="image" src="https://github.com/user-attachments/assets/0afaab53-ed01-4489-becc-97c83ca020fe" />


**Question 7**
---


<img width="725" height="416" alt="image" src="https://github.com/user-attachments/assets/ff95114a-44d8-48a8-a82f-60089284cdfd" />

sql
```
SELECT p.*
FROM patients AS p
INNER JOIN test_results AS t
    ON p.patient_id = t.patient_id
WHERE t.test_name = 'X-Ray'
  AND t.result = 'Normal';
```

**Output:**


<img width="650" height="324" alt="image" src="https://github.com/user-attachments/assets/90f0f5ce-39cb-4a25-b5bb-c3b08a0552cd" />


**Question 8**
---


<img width="724" height="405" alt="image" src="https://github.com/user-attachments/assets/272b683c-58ec-4f5b-ae7e-d0a22ed4d401" />

sql
```
SELECT 
    c.cust_name,
    c.city,
    c.grade,
    s.name AS Salesman,
    s.city
FROM customer AS c
INNER JOIN salesman AS s
    ON c.salesman_id = s.salesman_id
ORDER BY c.customer_id ASC;
```

**Output:**


<img width="651" height="419" alt="image" src="https://github.com/user-attachments/assets/67acfb4d-2858-49ae-902b-f871054e724c" />



**Question 9**
---


<img width="720" height="404" alt="image" src="https://github.com/user-attachments/assets/364d4924-c187-46f0-8c8b-3a12e4036bdb" />

sql
```
SELECT p.first_name
FROM patients AS p
INNER JOIN surgeries AS s
    ON p.patient_id = s.patient_id
WHERE s.surgery_date = '2024-01-15';
```

**Output:**


<img width="346" height="328" alt="image" src="https://github.com/user-attachments/assets/6fb02d64-fc71-4292-91fc-d0ded56bfa3c" />


**Question 10**
---


<img width="710" height="416" alt="image" src="https://github.com/user-attachments/assets/4a2a3f29-005f-4a82-9070-58b5b74b9d16" />

sql
```
SELECT 
    c.cust_name AS "Customer Name",
    c.city AS city,
    s.name AS Salesman,
    s.city AS city,
    s.commission
FROM customer AS c
INNER JOIN salesman AS s
    ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;
```

**Output:**


<img width="665" height="410" alt="image" src="https://github.com/user-attachments/assets/216534fa-2f2b-4cee-8159-dbd5f7c62597" />

**GRADES*


<img width="749" height="174" alt="image" src="https://github.com/user-attachments/assets/2afb0e73-5af3-42df-9804-4c92a888456a" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.

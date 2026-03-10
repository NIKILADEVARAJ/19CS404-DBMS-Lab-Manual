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
<img width="1088" height="547" alt="image" src="https://github.com/user-attachments/assets/3ec4da84-2333-4b6d-940b-275fb256c305" />

```sql
SELECT PatientID, COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID;
```

**Output:**

<img width="1243" height="737" alt="image" src="https://github.com/user-attachments/assets/d9ce5dcb-2757-4bc0-97f4-977d783d0610" />

**Question 2**
---
<img width="1142" height="650" alt="image" src="https://github.com/user-attachments/assets/b9e45301-38df-477e-b353-10af3f545a3d" />

```sql
SELECT DoctorID,count(*) AS TotalPrescriptions
FROM prescriptions
GROUP BY DoctorID;
```

**Output:**

<img width="1153" height="819" alt="image" src="https://github.com/user-attachments/assets/09a5997e-6173-4928-8cd5-b2c8677dad8f" />

**Question 3**
---
<img width="1133" height="594" alt="image" src="https://github.com/user-attachments/assets/94261099-e8ea-46f9-b6cc-c214ece1f8f4" />

```sql
SELECT
     SUBSTR(ValidityPeriod,1,4) AS ValidityYear,
     COUNT(DISTINCT PatientID)AS TotalPatients
FROM Insurance
GROUP BY SUBSTR(ValidityPeriod,1,4);
```

**Output:**

<img width="1121" height="462" alt="image" src="https://github.com/user-attachments/assets/5c040488-acc4-40c0-b0c4-176c5089d39a" />

**Question 4**
---
<img width="1032" height="469" alt="image" src="https://github.com/user-attachments/assets/2e7bda71-ee65-41a2-bec2-25254ec214f1" />

```sql
SELECT COUNT(*) AS COUNT
FROM employee
WHERE age>32;
```

**Output:**

<img width="976" height="407" alt="image" src="https://github.com/user-attachments/assets/7e503030-8c59-4042-baa8-1caedbd0c475" />

**Question 5**
---
<img width="1078" height="509" alt="image" src="https://github.com/user-attachments/assets/a15fa95a-8c6d-440c-a1cf-54bf781dce2e" />

```sql
SELECT COUNT(*) AS COUNT
FROM customer
WHERE city <> 'Noida';
```

**Output:**

<img width="864" height="403" alt="image" src="https://github.com/user-attachments/assets/be772a7e-80e7-431d-86af-597ea6ffb744" />

**Question 6**
---
<img width="1244" height="485" alt="image" src="https://github.com/user-attachments/assets/19915490-3096-4fdc-bee7-e212ba4993bc" />

```sql
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```

**Output:**

<img width="928" height="405" alt="image" src="https://github.com/user-attachments/assets/65bb9da1-e261-4997-aad3-9dd9bdef76d0" />

**Question 7**
---
<img width="868" height="475" alt="image" src="https://github.com/user-attachments/assets/b2aca6fa-f613-4118-a8a5-2eff3bdbca8a" />

```sql
SELECT avg(LENGTH(name)) AS avg_name_length
FROM customer
WHERE city='Chennai';
```

**Output:**

<img width="925" height="406" alt="image" src="https://github.com/user-attachments/assets/44187402-0fb6-46df-9b7a-121bd1b5e0d3" />

**Question 8**
---
<img width="1239" height="593" alt="image" src="https://github.com/user-attachments/assets/afbb3169-40ef-4b24-a8ea-db146a281b92" />

```sql
SELECT 
     (age/5)*5 AS age_group,
     MAX(salary)AS "MAX(salary)"
FROM customer1
GROUP BY (age/5)*5
HAVING MAX(salary)>8000;
```

**Output:**

<img width="1008" height="446" alt="image" src="https://github.com/user-attachments/assets/c9c0980d-c124-494f-9973-dc79a7e6e0b8" />

**Question 9**
---
<img width="1228" height="509" alt="image" src="https://github.com/user-attachments/assets/69f0c841-7378-4d0d-9e03-e50d99623abf" />

```sql
SELECT 
     age,
     MIN(income) AS "MIN(income)"
FROM employee
GROUP BY age
HAVING MIN(income)<400000;
```

**Output:**

<img width="1039" height="470" alt="image" src="https://github.com/user-attachments/assets/43e9a29e-6e1b-43dd-8f7f-5c14c3a15755" />

**Question 10**
---
<img width="1186" height="497" alt="image" src="https://github.com/user-attachments/assets/2aa4cccd-7e32-4c03-bd8e-7ac0534332f2" />

```sql
SELECT 
      jdate,
      SUM(workhour) AS "SUM(workhour)"
FROM employee1
GROUP BY jdate
HAVING SUM(workhour)>40;
```

**Output:**

<img width="1230" height="473" alt="image" src="https://github.com/user-attachments/assets/3760cd34-f646-49b1-842b-b25cf1560dbd" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

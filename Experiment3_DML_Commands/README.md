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
<img width="1142" height="555" alt="image" src="https://github.com/user-attachments/assets/b05a338a-9554-461c-b07f-775b6b488008" />

```sql
update products 
set reorder_lvl =40 
WHERE category='Grocery';
```

**Output:**

<img width="1220" height="493" alt="image" src="https://github.com/user-attachments/assets/cd908730-02d7-4fda-bbc7-042e9e2f1eba" />

**Question 2**
---
<img width="792" height="87" alt="image" src="https://github.com/user-attachments/assets/a62b8fd7-8ec0-4c98-a4b2-5a1594d6666c" />

```sql
UPDATE Customer 
SET grade=5
WHERE city='Chennai';
```

**Output:**

<img width="1236" height="572" alt="image" src="https://github.com/user-attachments/assets/c473b43b-feeb-4840-a8df-3e3e2a3d19fb" />

**Question 3**
---
<img width="1262" height="703" alt="image" src="https://github.com/user-attachments/assets/db34c22d-934e-43bd-94f2-74836007af7b" />

```sql
UPDATE Employees 
set salary=case
        when department_id=40 then round(salary*1.25)
        when department_id=90 then round(salary*1.15)
        when department_id=110 then round(salary*1.10 )
        else salary
end;
```

**Output:**

<img width="1223" height="548" alt="image" src="https://github.com/user-attachments/assets/57136b8f-6c01-491f-a817-abf4782d5b3a" />

**Question 4**
---
<img width="999" height="210" alt="image" src="https://github.com/user-attachments/assets/22e78e2c-6668-4e63-adeb-502b068a835c" />

```sql
update products
set product_name='Grapefruit'
where product_id=4;
```

**Output:**

<img width="1235" height="326" alt="image" src="https://github.com/user-attachments/assets/fe091648-ea59-4499-a414-7ff22ed33d2d" />

**Question 5**
---
<img width="1207" height="525" alt="image" src="https://github.com/user-attachments/assets/b317e9fb-22a5-4dc7-a97d-b3ed8ddc8773" />

```sql
DELETE FROM Customer 
where GRADE=2 and CUST_NAME LIKE 'M%' AND PAYMENT_AMT<3000;
```

**Output:**

<img width="1235" height="494" alt="image" src="https://github.com/user-attachments/assets/70c3f7e0-bd4d-4263-a099-af2abf49c538" />

**Question 6**
---
<img width="1216" height="574" alt="image" src="https://github.com/user-attachments/assets/8d254b4d-fffe-4842-befb-58594f6c69b9" />

```sql
DELETE FROM Customer
WHERE CUST_NAME LIKE '%Holmes%';
```

**Output:**

<img width="1235" height="503" alt="image" src="https://github.com/user-attachments/assets/84d460ec-1f8b-4692-95b6-ca4a6ce05e57" />

**Question 7**
---
<img width="1275" height="714" alt="image" src="https://github.com/user-attachments/assets/eedf085b-c912-4a81-85ff-fe799bb40d94" />

```sql
DELETE FROM Customer 
WHERE CUST_COUNTRY='India' AND CUST_CITY <> 'Chennai';
```

**Output:**

<img width="1293" height="790" alt="image" src="https://github.com/user-attachments/assets/66fe6a83-e77d-4b3d-a8c4-f86aaed5ca28" />

**Question 8**
---
<img width="964" height="440" alt="image" src="https://github.com/user-attachments/assets/0bf5f638-6817-43bf-a710-42e4149d08f3" />

```sql
SELECT order_no,order_date,purch_amt
FROM orders
where salesman_id=5001;
```

**Output:**

<img width="962" height="486" alt="image" src="https://github.com/user-attachments/assets/a396411a-0e75-4242-a418-6bb972b2e988" />

**Question 9**
---
<img width="1120" height="538" alt="image" src="https://github.com/user-attachments/assets/bc29031b-9d76-4dd7-ae74-e3783786e422" />

```sql
SELECT * FROM Patients
WHERE first_name LIKE 'A%';
```

**Output:**

<img width="1231" height="468" alt="image" src="https://github.com/user-attachments/assets/919fb05d-2da4-4c44-a7cf-254817fdec13" />

**Question 10**
---
<img width="1131" height="598" alt="image" src="https://github.com/user-attachments/assets/381c81ee-43c3-4da1-94e2-b9db09343f0e" />

```sql
SELECT id,value1,
      CASE
      WHEN value1%2=0 then 'Even'
      else 'Odd'
      end as parity
from Calculations;
```

**Output:**

<img width="1239" height="573" alt="image" src="https://github.com/user-attachments/assets/d5a50e59-e994-45c2-8b0e-f0b45d36b854" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

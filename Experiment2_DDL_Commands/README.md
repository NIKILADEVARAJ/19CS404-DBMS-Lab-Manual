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
<img width="1230" height="287" alt="image" src="https://github.com/user-attachments/assets/2e7feeb7-16c5-4952-a312-f95386513575" />



```sql
INSERT INTO Books(ISBN,Title,Author,Publisher,Year)
VALUES('978-1234567890','Data Science Essentials','Jane Doe','TechBooks',2024)
```

**Output:**

<img width="1241" height="350" alt="image" src="https://github.com/user-attachments/assets/82eb23b5-99a9-495e-8777-dd516bc2acfe" />

**Question 2**
---
<img width="1210" height="390" alt="image" src="https://github.com/user-attachments/assets/56be724e-26e5-4292-a33b-103fbf2faccf" />

```sql
CREATE TABLE Attendance(
AttendanceID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
AttendanceDate DATE,
Status TEXT CHECK(Status IN('Present','Absent','Leave')),
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

<img width="1237" height="393" alt="image" src="https://github.com/user-attachments/assets/5f049958-e018-4d41-868a-3662f8f42713" />

**Question 3**
---
<img width="1213" height="627" alt="image" src="https://github.com/user-attachments/assets/f8a028c1-8141-43eb-98c2-084bf32e9ae5" />

```sql
ALTER TABLE customer
RENAME COLUMN city TO location;
```

**Output:**

<img width="1233" height="444" alt="image" src="https://github.com/user-attachments/assets/34e394f4-ef82-49d0-8d2b-680a1fab7d4c" />

**Question 4**
---
<img width="885" height="348" alt="image" src="https://github.com/user-attachments/assets/67441417-5e7b-4459-a9aa-8cba5deee987" />

```sql
INSERT INTO Products(ProductID, ProductName, Price, Stock)
SELECT ProductID, ProductName, Price, Stock 
FROM Discontinued_products;
```

**Output:**

<img width="1231" height="386" alt="image" src="https://github.com/user-attachments/assets/bc5d82da-2d9e-479c-8d6b-adececb50173" />

**Question 5**
---
<img width="1129" height="408" alt="image" src="https://github.com/user-attachments/assets/679f0083-7f5f-496e-a5e5-90607e455ec5" />

```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE
);
```

**Output:**

<img width="1242" height="479" alt="image" src="https://github.com/user-attachments/assets/3ecd26a6-4f3c-4c97-bc05-47283ac828ed" />

**Question 6**
---
<img width="1128" height="398" alt="image" src="https://github.com/user-attachments/assets/6bb5d982-7019-49a2-8ff4-3a26b82e5632" />

```sql
INSERT INTO  Products (Name,Category,Price,Stock)
VALUES 
     ("Smartphone",'Electronics',800,150),
     ("Headphones",'Accessories',200,300);
```

**Output:**

<img width="1224" height="444" alt="image" src="https://github.com/user-attachments/assets/10a04242-ac1d-4759-93f3-8fa618349cd0" />

**Question 7**
---
<img width="1232" height="350" alt="image" src="https://github.com/user-attachments/assets/c4490c6c-45c8-4187-8a99-142b407d85ec" />

```sql
CREATE TABLE Shipments(
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY (OrderID) REFERENCES Orders(orderID)
);
```

**Output:**

<img width="1218" height="329" alt="image" src="https://github.com/user-attachments/assets/9d049ca5-31c6-4a18-aee6-91e06299ceda" />

**Question 8**
---
<img width="1135" height="380" alt="image" src="https://github.com/user-attachments/assets/46155b32-7595-43b5-a0f9-4181bae00d9b" />

```sql
INSERT INTO Employee (EmployeeID,Name,Position)Values(4,"Emily White","Analyst");
```

**Output:**

<img width="1224" height="404" alt="image" src="https://github.com/user-attachments/assets/33a5cab3-6b4d-413e-aee3-32b8f95d1f86" />

**Question 9**
---
<img width="1216" height="493" alt="image" src="https://github.com/user-attachments/assets/e75d83dc-b128-420e-ab1d-730424cb14a9" />

```sql
CREATE TABLE products(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10,2) NOT NULL,
discount DECIMAL(10,2) DEFAULT 0,
CHECK (list_price>=discount),
CHECK (discount>=0),
CHECK (list_price>=0)
);
```

**Output:**

<img width="1234" height="373" alt="image" src="https://github.com/user-attachments/assets/34ccafc9-d101-4048-a432-7a93bf41f677" />

**Question 10**
---
<img width="986" height="458" alt="image" src="https://github.com/user-attachments/assets/eef5cd2e-63b9-4175-9796-2aaacb3aa0f2" />

```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(202,"Ella King","F","Chemistry",87),
(203,"James Bond","M","Literature",78);
```

**Output:**

<img width="1221" height="361" alt="image" src="https://github.com/user-attachments/assets/60f4ce8e-3da0-4c1d-b486-af940f41e3da" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

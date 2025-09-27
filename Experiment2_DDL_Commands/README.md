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

<img width="1184" height="362" alt="Screenshot 2025-09-27 081952" src="https://github.com/user-attachments/assets/5d0e0574-e136-4f51-9874-e4f69d049dea" />

**Query**
```sql
CREATE table Departments(
DepartmentID INTEGER,
DepartmentName TEXT
);
```

**Output:**

<img width="1218" height="358" alt="Screenshot 2025-09-27 082155" src="https://github.com/user-attachments/assets/ddb5cd54-e02a-409c-91a0-4f4adb2e73ae" />

**Question 2**
---
<img width="1249" height="237" alt="Screenshot 2025-09-27 082216" src="https://github.com/user-attachments/assets/1937307b-7288-4f49-bb89-3b006abbbc21" />

**Query**
```sql
INSERT into Student_details(RollNo,Name,Gender,Subject,MARKS)
VALUES(201,"David Lee","M","Physics",92);
```

**Output:**

<img width="1216" height="267" alt="Screenshot 2025-09-27 082246" src="https://github.com/user-attachments/assets/71ce5118-d974-4188-a103-d5916e002690" />

**Question 3**
---
<img width="979" height="425" alt="Screenshot 2025-09-27 082712" src="https://github.com/user-attachments/assets/b907a0a6-d205-4903-84ce-56154525a3aa" />

**Query**
```sql
ALTER table employee
RENAME COLUMN id TO employee_id;
```

**Output:**

<img width="1212" height="306" alt="Screenshot 2025-09-27 082728" src="https://github.com/user-attachments/assets/3e4459a1-ccb8-47d9-a4a3-b70ab697c3c1" />


**Question 4**
---

<img width="800" height="384" alt="Screenshot 2025-09-27 082742" src="https://github.com/user-attachments/assets/05b27f34-6448-41fc-ba99-fe46c7b4bbfb" />

**Query**
```sql
INSERT into Employee(EmployeeID,Name,Position,Department,Salary)
VALUES(2,'John Smith','Developer','IT',75000);
INSERT into Employee(EmployeeID,Name,Position,Department,Salary) 
VALUES(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1208" height="385" alt="Screenshot 2025-09-27 082756" src="https://github.com/user-attachments/assets/e66b6006-9ea4-482c-8385-0fcab1629373" />

**Question 5**
---
<img width="764" height="356" alt="Screenshot 2025-09-27 082807" src="https://github.com/user-attachments/assets/4d449fa9-77e1-46fe-9dd6-34570f5ed3a8" />

**Query**
```sql
CREATE table Products(
ProductID Primary Key,
ProductName NOT NULL,
Price REAL CHECK(Price>0),
Stock INTEGER CHECK(Stock>=0)
);
```

**Output:**

<img width="1207" height="338" alt="Screenshot 2025-09-27 082833" src="https://github.com/user-attachments/assets/78972368-59fa-4c55-810d-f2bfb1e2726c" />


**Question 6**
---

<img width="1220" height="403" alt="Screenshot 2025-09-27 083201" src="https://github.com/user-attachments/assets/4c9532d5-9484-4645-a73a-858303c479d3" />

**Query**
```sql
CREATE table Products(
ProductID INTEGER primary key,
ProductName TEXT unique NOT NULL,
Price REAL CHECK(Price>0),
StockQuantity INTEGER CHECK(StockQuantity>0)
);
```

**Output:**

<img width="1204" height="328" alt="Screenshot 2025-09-27 083225" src="https://github.com/user-attachments/assets/1b409d32-f830-4f89-b90c-6e5ed45e5555" />


**Question 7**
---

<img width="987" height="303" alt="Screenshot 2025-09-27 083243" src="https://github.com/user-attachments/assets/dab32f5e-5869-4633-b734-c523b62ddc3e" />

**Query**
```sql
ALTER table employee add designation varchar(50);
```

**Output:**

<img width="1214" height="333" alt="Screenshot 2025-09-27 083312" src="https://github.com/user-attachments/assets/8ce84ed1-65c9-4c4e-88ac-fce6122b8558" />

**Question 8**
---

<img width="744" height="348" alt="Screenshot 2025-09-27 083324" src="https://github.com/user-attachments/assets/48d5d1fe-bf5d-4aa6-ab36-2c48d4de359a" />

**Query**
```sql
INSERT into Products(ProductID,ProductName,Price,Stock) 
SELECT ProductID,ProductName,Price,Stock
FROM Discontinued_products 
```

**Output:**

<img width="1225" height="364" alt="Screenshot 2025-09-27 083348" src="https://github.com/user-attachments/assets/f7cb7031-9503-45d0-9420-b6a6e1e831cb" />

**Question 9**
---

<img width="1201" height="352" alt="Screenshot 2025-09-27 083419" src="https://github.com/user-attachments/assets/1b6b1e34-fb06-4327-a884-201d385cc7af" />

**Query**
```sql
CREATE table Shipments(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
foreign key (SupplierID) references Suppliers(SupplierID) 
foreign key (OrderID) references Orders(OrderID) 
);
```

**Output:**

<img width="1220" height="307" alt="Screenshot 2025-09-27 083434" src="https://github.com/user-attachments/assets/968ec386-e974-4134-921c-7cf4f8be142e" />


**Question 10**
---

<img width="1022" height="442" alt="Screenshot 2025-09-27 083447" src="https://github.com/user-attachments/assets/50e4274b-5f75-4db3-9de1-a8bd51b0c05c" />

**Query**
```sql
CREATE table item(
item_id TEXT Primary Key,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT CHECK(length(icom_id)=4),
foreign key(icom_id) references company(com_id)
  on update cascade
  on delete cascade
);
```

**Output:**

<img width="1198" height="369" alt="Screenshot 2025-09-27 083458" src="https://github.com/user-attachments/assets/f45604d3-02f4-4a71-825b-c435e1a5be0b" />

## Module 1 Homechallenge Grade: 

<img width="1064" height="74" alt="Screenshot 2025-09-27 084309" src="https://github.com/user-attachments/assets/3e37c480-21a6-4d29-a1bf-9870bfcdf306" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

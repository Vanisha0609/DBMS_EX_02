# EXP No : 2                                                                                                                                                                         
# DATE : 07/03/2024

# AIM:
To study and implement DDL commands and different types of constraints.

# THEORY:

## 1. CREATE: 
This is used to create a new relation (table) 
### Syntax:
CREATE TABLE (field_1 data_type(size),field_2 data_type(size), .. . );
           
## 2. ALTER:
This is used to add some extra fields into existing relation. 
### Syntax: 
ALTER TABLE relation_name ADD (new field_1 data_type(size) );
      
#### (a)ALTER TABLE ...ADD...: 
ALTER TABLE std ADD (Address CHAR(10));
#### (b)ALTER TABLE...MODIFY...:
ALTER TABLE relation_name MODIFY (field_1 newdata_type(Size)
#### (c) ALTER TABLE..DROP....
ALTER TABLE relation_name DROP COLUMN (field_name); 
#### (d)ALTER TABLE..RENAME...:
ALTER TABLE relation_name RENAME COLUMN (OLD field_name) to (NEW field_name);

## 3. DROP TABLE: 
This is used to delete the structure of a relation. It permanently deletes the records in the table. 
### Syntax: 
DROP TABLE relation_name;  

## 4.RENAME:
It is used to modify the name of the existing database object.
### Syntax: 
 RENAME TABLE old_relation_name TO new_relation_name;                  

# CONSTRAINTS:
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE statement) or after the table is created (using ALTER TABLE statement). 
## 1. NOT NULL: 
When a column is defined as NOTNULL, then that column becomes a mandatory column. It implies that a value must be entered into the column if the record is to be accepted for storage in the table. 
### Syntax: 
CREATE TABLE Table_Name (column_name data_type (size) NOT NULL, );
## 2. UNIQUE:
The purpose of a unique key is to ensure that information in the column(s) is unique i.e. a value entered in column(s) defined in the unique constraint must not be repeated across the column(s). A table may have many unique keys. 
### Syntax:
CREATE TABLE Table_Name(column_name data_type(size) UNIQUE, ….);

## 3. CHECK: 
Specifies a condition that each row in the table must satisfy. To satisfy the constraint, each row in the table must make the condition either TRUE or unknown (due to a null). 
### Syntax: 
CREATE TABLE Table_Name(column_name data_type(size) CHECK(logical expression), ….); 

## 4. PRIMARY KEY:
A field which is used to identify a record uniquely. A column or combination of columns can be created as primary key, which can be used as a reference from other tables. A table contains primary key is known as Master Table.  
- It must uniquely identify each record in a table.  
- It must contain unique values.  
- It cannot be a null field. 
- It cannot be a multi port field.  
- It should contain a minimum number of fields necessary to be called unique. 
### Syntax: 
CREATE TABLE Table_Name(column_name data_type(size) PRIMARY KEY, ….);

## 5. FOREIGN KEY: 
It is a table level constraint. We cannot add this at column level. To reference any primary key column from other table this constraint can be used. The table in which the foreign key is defined is called a detail table. The table that defines the primary key and is referenced by the foreign key is called the master table. 
### Syntax: 
CREATE TABLE Table_Name(column_name data_type(size) FOREIGN KEY(column_name) REFERENCES table_name);

## 6. DEFAULT : 
The DEFAULT constraint is used to insert a default value into a column. The default value will be added to all new records, if no other value is specified. 
### Syntax: 
CREATE TABLE Table_Name(col_name1,col_name2,col_name3 DEFAULT ‘’);

# MODULE:
## QUESTION 1:


![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/90700199-a8c1-4d0f-b5c9-77ed10b17d71)



#### QUERY:
```
CREATE TABLE Orders (
    OrderID INTEGER PRIMARY KEY,
    OrderNumber INTEGER,
    PersonID INTEGER,
    FOREIGN KEY (PersonID) REFERENCES Person(PersonID)
);
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/fda3faf7-0dbe-4fcc-b5dc-e8e759e49038)



## QUESTION 2:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/1fea25ef-8186-4e02-9927-2fa0fa8473ba)


#### QUERY:
```
CREATE TABLE employeedetails (
    id INT,
    first_name TEXT,
    last_name TEXT,
    FOREIGN KEY (id) REFERENCES customer(id)
);
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/258af1c4-cfd6-44fa-b932-fe90a05bafed)

## QUESTION 3:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/0c3197f6-3355-4745-8bee-8e880410fd9d)


#### QUERY:
```
CREATE TABLE Students (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name varchar(50),
    address varchar(30),
    grades varchar(10),
    phone number(10)
);
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/7b78f75d-e16f-4b8e-bb45-6ddb5dd04b55)


## QUESTION 4:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/852c52ea-e0b8-4ab8-9f77-21cdfe3b3d8a)


#### QUERY:
```
CREATE TABLE IF NOT EXISTS Students (
    id NUMBER,
    grade VARCHAR(50)
);
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/b64f6180-5279-439e-8fae-beb96b566e08)

## QUESTION 5:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/b61a4da5-7f16-4562-a8cd-1e39fe60a1ff)

#### QUERY:
```
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/c66924d7-a23b-4330-b71f-b552d8211250)

## QUESTION 6:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/18855c5d-0580-4336-beea-19c673574e15)

#### QUERY:
```
ALTER TABLE customer
ADD COLUMN email VARCHAR(5,2);
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/a80672e5-0f6a-4654-920f-60ed41a67771)

## QUESTION 7:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/e7dbb085-e152-4ad1-871e-c23d4effd46e)

#### QUERY:
```
ALTER TABLE employee
RENAME COLUMN id TO employee_id;
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/0e5835f7-9505-4e90-b7d2-ab26df5b78e7)

## QUESTION 8:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/89c92685-7a0a-4ee4-b4b7-b5be13e31768)

#### QUERY:
```
INSERT INTO Employee_db (EmployeeID, FirstName, LastName, Salary, HireDate)
VALUES 
    ('2', 'Jane', 'Smith', '60000', '2021-04-10'),
    ('3', 'Bob', 'Johnson', '55000','2022-06-07'),
    ('4', 'Alice', 'Williams', '70000', '2023-03-10'),
    ('5', 'Charlie', 'Brown', '48000', '2020-04-20');

```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/44bbf1a7-7f00-45fc-aafc-8be403f1cf8e)

## QUESTION 9:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/b2253974-c505-49f9-8b11-708ebebf3887)


#### QUERY:
```
INSERT INTO ShiftSchedule (EmployeeID, EmployeeName, ShiftStartTime, ShiftEndTime)
VALUES 
    (104, 'David Wilson', '07:45:00', '16:15:00'),
    (105, 'Emma Hall', '10:00:00', '18:30:00'),
    (106, 'Frank White', '12:30:00', '21:00:00'),
    (107, 'Grace Miller', '14:15:00', '22:45:00'),
    (108, 'Henry Taylor', '09:00:00', '17:30:00');
```
#### OUTPUT:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/7f855ebb-cf85-4fd8-966c-21e36f144953)

## QUESTION 10:

![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/e4a2b129-7172-4e12-a07e-76e52644873a)

#### QUERY:
```
INSERT INTO DestinationTable (ID, Name, Age)
SELECT ID, Name, Age
FROM SourceTable
WHERE Name = 'Kumar';
```
#### OUTPUT:
![image](https://github.com/Vanisha0609/DBMS_EX_02/assets/119104009/e1067f37-fa9e-438f-888a-0cbbc2988b54)

# RESULT:
Thus, we studied and implemented DDL commands and different types of constraints. 



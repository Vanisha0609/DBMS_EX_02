# EXP No.2                                                                                                                                                                               
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

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/705195e6-3a5a-458c-b898-9f481e253561)

#### QUERY:
```
CREATE TABLE Students (
    rollno INTEGER PRIMARY KEY AUTOINCREMENT,
    stu_name VARCHAR(50),
    dob DATE,
    year VARCHAR(30)
);

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/58c6567f-36d7-430b-ae68-d98b7b2efca2)

## QUESTION 2:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/db6d3054-cb70-4d46-ba23-badd36bde721)

#### QUERY:
```
CREATE TABLE Students (
    rollno INTEGER PRIMARY KEY AUTOINCREMENT,
    stu_name VARCHAR(50),
    year VARCHAR(30)
);

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/4d9db0a6-4154-4fda-82cd-7d55ca6c7d57)

## QUESTION 3:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/5356bd72-5ac1-4cc2-bc3a-b17b56e3a679)

#### QUERY:
```
CREATE TABLE Orders (
    OrderID INTEGER ,
    OrderNumber INTEGER,
    ProductName Varchar(30),
    PersonID INTEGER NOT NULL
);

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/c27f46ff-4215-485d-9414-c1c789c623d2)

## QUESTION 4:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/227a7a6e-823e-48bb-bcc9-f14c2f3ac8f6)

#### QUERY:
```
CREATE TABLE employeedetails AS
SELECT id, first_name, last_name FROM customer WHERE 1=0;

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/8efc59f3-c9a7-4917-b43a-eec295e4e03e)


## QUESTION 5:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/f2ee9bda-0d37-4092-a90a-4635c0a0bba5)

#### QUERY:
```
ALTER TABLE employee RENAME COLUMN id TO emp_id;
```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/710ee542-195e-4d78-9b8a-6ba4dd52163c)

## QUESTION 6:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/304092a2-d01e-4a5d-bfb9-ac73d446e104)

#### QUERY:
```
ALTER TABLE employee ADD COLUMN birth_date date;
```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/8eecbf68-b45b-49c8-bd2c-ecad8513612e)

## QUESTION 7:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/7cdf752d-19b9-4e3a-8cb7-aeb6465a47da)

#### QUERY:
```
ALTER TABLE Companies
ADD COLUMN designation varchar(50);

ALTER TABLE Companies
ADD COLUMN net_salary number;

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/66ea018a-6b6c-43dd-a607-7cbab8ff09ae)

## QUESTION 8:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/206430aa-7284-4e33-803a-30d096b8659c)

#### QUERY:
```
INSERT INTO Student (RollNo, Name, Gender, Subject, MARKS)
VALUES 
    (3, 'Jeni', 'Female', 'English', 96),
    (4, 'Bob Johnson', 'Male', 'History', 90),
    (5, 'Sharvesh', 'Male', 'Botany', 97),
    (6, 'Mathew', 'Male', 'Science', 85);

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/318b617c-abda-4f19-a442-eebd74a87446)

## QUESTION 9:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/7ef3ae5a-f82c-4222-9fa9-e2e6dc2a3974)

#### QUERY:
```
INSERT INTO new_customers (customer_id, name, email)
SELECT customer_id, name, email
FROM old_customers
WHERE email LIKE '%@gmail.com';

```
#### OUTPUT:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/c09ea269-ca76-4419-b0e0-d7033031a801)

## QUESTION 10:

![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/74daad6c-7eef-4a43-a0e5-2f911a9b3941)

#### QUERY:
```
INSERT INTO new_customers (customer_id, name, email)
SELECT customer_id, name, email
FROM old_customers
WHERE email = 'abc@gmail.com';
```
#### OUTPUT:
![image](https://github.com/Mena-Rossini/DBMS_EX_02/assets/102855266/4d5d3d9e-a668-4044-92c9-673eb159e5b4)

# RESULT:
Thus, we studied and implemented DDL commands and different types of constraints. 



# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE: 16/08/23
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY:
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:
### 1) Create a database studentdb

### SQL QUERY:
```sql
create database studentdb;
```
### OUTPUT:

![create db](https://github.com/Kayalvizhi02/DBMS/assets/75413726/b674fd6b-866a-4539-945f-be275bb0e920)

### 2) Create a table student with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY:
```sql
create table student(reg_no int,name varchar(20),age int,address varchar(255),ph_no int);
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/a83422d5-8ea5-495c-82c6-fd0aedf9f68b)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY: 
```sql
alter table student add department varchar(20);
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/e505cc5b-9d9c-4319-ab57-3acdafd0e5ef)


### 4) Drop the student table
 
### SQL QUERY: 
```sql
drop table student;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/9281d38b-f268-41ca-93de-abb8d3451483)

### 5) Delete the student table using truncate keyword

### SQL QUERY: 
```sql
truncate table student;
```
### OUTPUT:

![truncate table](https://github.com/Kayalvizhi02/DBMS/assets/75413726/219862cc-9a2c-47cb-b487-a987fcff0a9c)

### 6) Rename the student table to mystudent

### SQL QUERY: 
```sql
rename table student to mystudent;
```
### OUTPUT:

![rename table](https://github.com/Kayalvizhi02/DBMS/assets/75413726/9f588b4f-0ee8-4b89-8a0a-acd250199ab0)


## Result:
Thus the basic DDL commands in SQL are executed. 



# EXP NO 4: Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE: 30/08/23
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY:
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```sql
 create table employee(emp_id int,name varchar(255),address varchar(255));
 ```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/c4c6e700-c519-4021-a0b8-6f80714265a7)

### Q2) Insert three rows into emploee table 

### QUERY:
```sql

insert into employee(emp_id,name,address)values(1,'Kayal','123 Main st');
insert into employee(emp_id,name,address)values(2,'Harshini','456 Oakst');
insert into employee(emp_id,name,address)values(3,'Charu','345 Oak st');
```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/6b8aa5c1-df56-43b8-9f6b-bc126865ff07)


### Q3) Start the transaction and create a save point s1.

### QUERY:

```sql

START TRANSACTION;
SAVEPOINT s1;
```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/fde802d5-7e62-494d-a0f3-66925f79c898)

### Q4) Perform insertion into employee table.

### QUERY:
```sql

insert into employee (emp_id, name, address)values(4, 'Beulah', '567 Pine St');
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/18506561-f1dd-4785-8acd-f0206fc872e2)


### Q6)	Display the employee table and create a save point s2 .


### QUERY:
```sql

SELECT * FROM employee;
SAVEPOINT s2;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/745c60cd-ddbb-4318-8ac7-db04a54a6814)

### Q7)	Perform updation on any one of the row.


### QUERY:
```sql

UPDATE employee SET address = '101 Oak Ave' WHERE emp_id = 1;
```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/c03a03da-6d9e-47ed-9706-fe60647f2e55)


### Q8) Display the employee table and rollback to  save point s2 


### QUERY:
```sql

SELECT * FROM employee;
ROLLBACK TO s2;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/160f6211-35f8-4235-a2be-665635c15244)

### Q9) Display the employee table and commit the changes; 


### QUERY:
```sql

SELECT * FROM employee;
COMMIT;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/c525cb78-aae0-41b1-9c89-bba6ad09e8b0)

### Q10) Rollback to save point s1;


### QUERY:
```sql

ROLLBACK TO s1;

```
### OUTPUT:


### Q11)	Create a new user and grant access to any one database with "insert and update"


### QUERY:
```sql

CREATE USER new_user IDENTIFIED BY 'password';
GRANT INSERT, UPDATE ON database_name.* TO new_user;
```

### OUTPUT:


### Q12) Check the user access and display the result 


### QUERY:
```sql

SHOW GRANTS FOR new_user;

```
### OUTPUT:

### Q13) Revoke the privillages.

### QUERY:
```sql

REVOKE INSERT, UPDATE ON database_name.* FROM new_user;
DROP USER new_user;

```
### OUTPUT:


## RESULT :
Thus the basic TCL and DCL commands are executed.

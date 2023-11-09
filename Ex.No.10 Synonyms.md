# EXP NO 8: SYNONYMS AND ASSERTIONS IN SQL 

## AIM:
To create a student database and create a synonym and assertions.

## THEORY:
## SYNONYM:
<div align="justify">
A SYNONYM provides another name for database object, referred to as original object, that may exist on a local or another server.
</div>
## ASSERTIONS:
<div align="justify">
* An assertion is a piece of SQL which makes sure a condition is satisfied, else or it stops the action being taken on a database.
* An assertion is a constraint that might be dependent upon multiple rows of multiple tables.
</div>

## Query:
### 1) Create a table EMPLOYEE and perform insertion of two rows.

### SQL QUERY:
```sql
CREATE TABLE EMPLOYEE (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(255),
    employee_salary DECIMAL(10, 2)
);

INSERT INTO EMPLOYEE (employee_id, employee_name, employee_salary)
VALUES (1, 'Kayal', 50000.00);

INSERT INTO EMPLOYEE (employee_id, employee_name, employee_salary)
VALUES (2, 'Dolly', 60000.00);
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/9084c1ab-02ab-496a-9218-4fa94bb57df0)

### 2) Create a synonym S1 for EMPLOYEE  table.

### SQL QUERY: 
```sql
CREATE SYNONYM S1 FOR EMPLOYEE;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/23824cf0-b6a5-4b8f-9e79-8942784ea32b)


### 3) Display the EMPLOYEE  table using synonym S1.
 
### SQL QUERY: 
```sql
SELECT * FROM S1;
```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/941c7b26-6122-40f1-91cc-7dae211a2263)


### 4) Drop the synonym.

### SQL QUERY: 
```sql
DROP SYNONYM S1;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/61fc8b12-85f3-4b50-aa0e-0ab9f3e77fd7)


### 5) Create a supplier table and create a sequence S2 for supplier table id.

### SQL QUERY: 
```sql
CREATE TABLE SUPPLIER (
    supplier_id INT PRIMARY KEY,
    supplier_name VARCHAR(255)
);

CREATE SEQUENCE S2;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/481dc4cd-fecf-45e2-8a46-6b7d187e222a)

### 6) insert the data into supplier table use sequence.

### SQL QUERY: 
```sql
INSERT INTO SUPPLIER (supplier_id, supplier_name)
VALUES (S2.NEXTVAL, 'AB Suppliers');

INSERT INTO SUPPLIER (supplier_id, supplier_name)
VALUES (S2.NEXTVAL, 'CD Suppliers');
```

### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/4f6fd96d-feac-489b-9c60-b2ddf8b79281)

### 7) Drop the sequence

### SQL QUERY: 
```sql
DROP SEQUENCE S2;
```

### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/af12703c-e4b3-483d-a82f-0f9974c9b0d2)

## RESULT :
Thus the sequence and synonym created and used in SQL.

# EXP NO 5: SubQueries, Views and Joins 

## AIM:
To use SubQueries, Views and Joins in SQL 
## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```
## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'SCOTT', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-RR'), 3000, 20, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7934, 'MILLER', 'CLERK', 7782, TO_DATE('23-JAN-82', 'DD-MON-RR'), 1300, 10, 10);
```

## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```
## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```

### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.


### QUERY:
```sql
SELECT ENAME FROM EMP WHERE SAL > (SELECT SAL FROM EMP WHERE EMPNO = 7566);

```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/b209d923-e2cf-449e-a54a-32d9018c0526)


### Q2) List the ename,job,sal of the employee who get minimum salary in the company.

### QUERY:
```sql
SELECT ENAME, JOB, SAL FROM EMP WHERE SAL = (SELECT MIN(SAL) FROM EMP);
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/34dadaa9-768d-4bc4-957a-40f225828782)

### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:
```sql
SELECT ENAME, JOB FROM EMP WHERE DEPTNO = 10 AND JOB IN (SELECT JOB FROM EMP WHERE JOB = 'sales');
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/3b52cce3-3b4a-41ff-a2af-0f23362e7c24)

### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:
```sql
CREATE VIEW empv5 AS SELECT empno, ename, job FROM EMP WHERE deptno = 10;
SELECT ename FROM empv5;

```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/f07b0106-9341-4e44-be21-9c1f848b61f3)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/25e97817-7be1-4354-8846-359ae0b249bc)


### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:
```sql
CREATE VIEW empv30 AS SELECT empno AS "Employee Number", ename AS "Employee Name", sal AS "Salary" FROM EMP WHERE deptno = 30;
SELECT * FROM empv30;

```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/8b18b4cb-e4a2-48eb-aa72-0fa814b30ca0)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/82c26879-ba0d-4ceb-a7dd-b955da6d6b91)


### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:
```sql
UPDATE emp SET sal = sal * 1.1 WHERE job = 'CLERK';
SELECT empno, ename, job, sal FROM emp WHERE job = 'CLERK';

```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/ba0b244b-7a38-4120-a555-705a6259ba5c)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/519839c7-554c-412e-ab08-1d6f98d0e9c6)


## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```
## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick Rimando', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad Davis', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham Zusi', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian Green', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Fabian Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geoff Cameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jozy Altidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brad Guzan', 'London', NULL, 5005);
```
## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```
## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'James Hoog', 'New York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nail Knite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pit Alex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mc Lyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paul Adam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauson Hen', 'San Jose', 0.12);
```
### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

### QUERY:
```sql
SELECT s.name AS Salesman1, c.cust_name, c.city FROM Salesman1 s INNER JOIN Customer1 c ON s.city = c.city;
```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/490908c6-fe69-44a5-9e54-d135c4f6538c)

### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.


### QUERY:
```sql
SELECT c.cust_name AS Customer_Name, c.city AS Customer_City, s.name AS Salesman, s.commission FROM Customer1 c JOIN Salesman1 s ON c.salesman_id = s.salesman_id WHERE s.commission > 0.13 ORDER BY s.name ASC;
```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/519caea6-3a8b-4a25-8e84-f58711d67e6c)

### Q9) Perform Natural join on both tables

### QUERY:
```sql

SELECT * FROM Salesman1
NATURAL JOIN Customer1;

```
### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/d7e5a8db-3208-463a-a69b-c99f7168b819)

### Q10) Perform Left and right join on both tables

### QUERY:
```sql
SELECT * FROM Customer1
LEFT JOIN Salesman1 ON Customer1.salesman_id = Salesman1.salesman_id;
SELECT * FROM Customer1
RIGHT JOIN Salesman1 ON Customer1.salesman_id = Salesman1.salesman_id;
```

### OUTPUT:
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/34386d24-4c71-447f-a199-44f7a6bbeaa3)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/58bd582b-ee63-4d7d-87cf-1070576e9218)


## RESULT: 
Thus the basics of subqueries,views,joins are performed in SQL.

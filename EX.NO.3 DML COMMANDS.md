# EXP NO 3: Data Manipulation Language (DML) Commands and built in functions in SQL
### DATE:
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```sql
update manager 
set salary = salary + (salary * 10/100)
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/695ea2bf-4d0a-4e3d-92c9-2b106f92c923)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```sql

delete from manager 
where salary < 2750
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/cfbea0c9-1fb2-483d-a934-97fb3886c597)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```sql

select ename as "Name",salary*12 as annualsalary from manager;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/022940df-673d-4083-8b72-fd30b83e7fec)


### Q5)	List the names of Clerks from emp table.
### QUERY:
```sql

select ename from manager where designation = 'clerk';
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/17a7578f-a1bc-4f52-9453-b35051adf0a2)


### Q6)	List the names of employee who are not Managers.

### QUERY:
```sql

select ename from manager where designation != 'manager';
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/f51a1b98-903d-4b1d-9ec1-bd4d2adeedec)


### Q7)	List the names of employees not eligible for commission.

### QUERY:
```sql

select ename from manager where commission = 0;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/4530ae3c-5643-4429-b586-4446186ace86)


### Q8)	List employees whose name either start or end with ‘s’.

### QUERY:
```sql

select ename from manager where ename like 'S%' or ename like '%S';
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/4bee5180-d4e1-4079-ae81-db4632d6d233)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```sql

select Hiredate,ename,designation,deptno from manager order by Hiredate;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/b77acac0-d488-4d8a-a16f-afe59336a314)


### Q10) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```sql

select * from manager where Hiredate < '30-Sept-81';
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/6d9f20ab-08af-46ec-9d48-a33e0278ac30)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```sql

select ename,deptno,salary from manager order by deptno,salary desc;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/b67da2cf-baac-4af6-a934-8d541cb35c4e)

### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```sql

select ename from manager where deptno != 30 and deptno != 40 and deptno != 10;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/3d79c086-3293-4c60-bda1-227d9b7033f9)


### Q13) Find number of rows in the table EMP

### QUERY:
```sql

select count (*) as count_ename from manager;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/da48ad52-f164-43cc-8c1a-9b7ffddc0fb0)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```sql

select avg(salary) as tot_salary from manager;
select min(salary) as min_salary from manager;
select max(salary) as max_salary from manager;
```
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/92c2995c-5739-4600-8434-7daa9b7bd5d1)
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/8209e182-700f-41c9-86cf-6b800fc5b45f)
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/f8540db5-be25-4a56-9171-4ab31e2090ab)



### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql

select designation,enumber from manager order by designation ,enumber desc;
``` 
### OUTPUT:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/577b6236-f8ea-4f95-8a2c-fa8f327b57d0)



## RESULT :
Thus the basic DML commands are executed.

# EXP NO 9: PL/SQL program using Triggers 
### DATE: 
### AIM: 
To create PL/SQL program to display new and old salary of customer when before/ after updation takes place. 

### Steps:
1. Create a trigger for each row when updation occurs.
2. Declare the variable in Declare section.
3. Start the begin section.
4. Calculate the salary changes.
5. Display the result 
6. End the begin section.

### Program:
### Create employee table:
```sql
CREATE TABLE customer (
  customerid NUMBER,
  customername VARCHAR(10),
  dept VARCHAR(10),
  salary NUMBER
);
```
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/94b1af13-baee-4bbe-a70f-162ab76a291d)

### Create salary_log table:
```sql
CREATE TABLE sal_log (
  log_id NUMBER GENERATED ALWAYS AS IDENTITY,
  customerid NUMBER,
  customername VARCHAR2(10),
  old_salary NUMBER,
  new_salary NUMBER,
  update_date DATE
);
```
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/368159c0-2d4a-456c-a27d-25319322207a)


### PL/SQL Trigger code:
```sql
CREATE OR REPLACE TRIGGER log_sal_update
BEFORE UPDATE ON customer
FOR EACH ROW
BEGIN
  IF :OLD.salary != :NEW.salary THEN
    INSERT INTO sal_log (customerid, customername, old_salary, new_salary, update_date)
    VALUES (:OLD.customerid, :OLD.customername, :OLD.salary, :NEW.salary, SYSDATE);
  END IF;
END;

insert into customer values(1,'Kayal','HR',100000);
insert into customer values(2,'Harshu','SALES',500000);

UPDATE customer
SET salary = 60000
WHERE customerid = 1;

SELECT * FROM customer;

SELECT * FROM sal_log;
```
### Output:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/adc5fbef-45ad-4b7c-a1d6-97153229df57)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/a3f6ede1-00ce-4e24-968e-fb5029265329)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/060f29e8-d91c-4de4-ad8c-313982075741)

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/3240e506-6c45-43e5-868e-f65db26e2f21)
![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/ff7db464-384e-482e-802c-21dfa2573768)


### Result:
Thust the program was performed sucessfully.

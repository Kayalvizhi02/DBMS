# EXP NO 8: PL/SQL program using Cursor 
### DATE: 
### AIM: 
To create PL/SQL program to display the customer table 

### Steps:
1. Declare the variable  in Declare section.
2. Fetch the variable with datatype similar to data type in cursor 
3. Create a cursor to select all rows from customers table.
4. Display the result 
5. End the begin section.

### Program:
### Create employee table:
```sql
CREATE TABLE customer (
  customerid NUMBER,
  customername VARCHAR(10),
  dept VARCHAR(10),
  salary NUMBER
);

INSERT INTO customer VALUES (1, 'Kayal', 'HR', 100000);
INSERT INTO customer VALUES (2, 'Charu', 'Sales', 80000);
select * from customer;
```
### Output:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/750b25de-e1b7-4ecf-8eef-5a5bd8e05c5d)

### PLSQL Cursor code:
```sql
DECLARE
   CURSOR customer_cursor IS
   SELECT customerid,customername,dept,salary
   FROM customer;
   customer_id NUMBER;
   customer_name VARCHAR(50);
   customer_dept VARCHAR(50);
   customer_salary NUMBER;
BEGIN
  OPEN customer_cursor;

  LOOP
    FETCH customer_cursor INTO customer_id, customer_name, customer_dept, customer_salary;

    EXIT WHEN customer_cursor%NOTFOUND;

    DBMS_OUTPUT.PUT_LINE('Customer ID: ' || customer_id);
    DBMS_OUTPUT.PUT_LINE('Customer Name: ' || customer_name);
    DBMS_OUTPUT.PUT_LINE('Department: ' || customer_dept);
    DBMS_OUTPUT.PUT_LINE('Salary: ' || customer_salary);
  END LOOP;

  CLOSE customer_cursor;
END;
```
### Output:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/490bc9d6-9bdf-4623-88bf-a82b1b5d5bce)

### Result:
Thust the program was performed sucessfully.

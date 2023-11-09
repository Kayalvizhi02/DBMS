# EXP NO 6: PL/SQL program to perform addition and subtraction of two number 
### DATE: 20/09/23

### AIM: 
To create PL/SQL program to perform addition and subtraction of two number.

### Steps:
1. Declare the variable a, b and necessary variables in Declare section.
2. Perform addition of two numbers
3. Perform subtraction of two numbers 
4. Display the result 
5. End the begin section.

### Program:
```sql
DECLARE
 a NUMBER := 50;
 b NUMBER := 25;
 c NUMBER;
BEGIN
 c:=a+b;
 dbms_output.Put_line('addition of two numbers is '||c);
 c:=a-b;
 dbms_output.Put_line('subtraction of two numbers is '||c);
END; 

```
### Output:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/2bba2bb6-85f3-4c21-8a16-12ee63fb70c7)

### Result:
Thust the program was performed sucessfully.

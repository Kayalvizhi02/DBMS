# EXP.NO 7: PL/SQL program -BIGGEST OF THREE NUMBERS  
### DATE: 
### AIM: 
To create PL/SQL program to find biggest of three numbers.

### ALGORITHM:
1. Declare the variable a, b, c and assign value in Declare section.
2. begin the section
3. Find biggest of three numbers 
4. 5. Display the result 
6. End the begin section.

### Program:
```sql
DECLARE
 a NUMBER := 55;
 b NUMBER := 65;
 c NUMBER := 75;
BEGIN
 IF a > b AND a > c THEN
 dbms_output.Put_line('Biggest number is '||a);
 ELSIF b > a AND b > c THEN
 dbms_output.Put_line('Biggest number is '||b);
 ELSE
 dbms_output.Put_line('Biggest number is '||c);
 END IF;
END;
```
### Output:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/9ff53321-0c19-4800-a11f-47d944875a00)


### Result:
Thust the program was performed sucessfully.

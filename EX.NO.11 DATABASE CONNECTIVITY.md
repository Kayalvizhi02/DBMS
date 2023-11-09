# EXP NO 11: DATA BASE CONNECTIVITY USING  MYSQL AND JAVA
### DATE: 
### AIM: To create database connectivity and display the employee table 

### Steps:
1. Install mysql,visual studio,jdk, extensions of java pack.
2. Create a employee table and insert the data into employee table  
3. Create a new java project in visual studio.
4. write a java progarm to perform the following 1.create a connection 2. fetch data and store it in result set 3. Display table rows. 4. Close the connection
5. Deploy the jar file in lib folder 
6. Run the program

### Program:
```java
package com.employees;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class App {
	public static void main(String[] args) throws SQLException {

		System.out.println("Connecting to DB");
		Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydb", "root", "Root@2005");

		System.out.println("Connection Successfull");

		Statement stmt = con.createStatement();
		ResultSet rs = stmt.executeQuery("Select * from employees");
		

		while (rs.next()) {
			System.out.println("id :" + rs.getInt("Emp_id"));
			System.out.println("name :" + rs.getString("Emp_name"));
			System.out.println("salary :" + rs.getInt("Emp_salary"));

		}
		con.close();
		System.out.println("Connection closed");

	}

}
```
### Output:

![image](https://github.com/Kayalvizhi02/DBMS/assets/75413726/cfb1fdfc-31c0-4bb9-99a5-8e01f999be24)

### Result:
Thust the database is connected and data displayed sucessfully.

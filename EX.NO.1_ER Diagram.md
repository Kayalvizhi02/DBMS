# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm:
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram: 

![BM Relational Schema](https://github.com/Kayalvizhi02/DBMS/assets/75413726/385f527c-64cd-461d-a443-1df399ed4d05)

### Relational model:

![BM Relational Schema](https://github.com/Kayalvizhi02/DBMS/assets/75413726/17d652a0-8cb0-4476-9225-61bc9a573b05)

### SQL DDL Schema:
```sql
CREATE TABLE Name
(
  Code INT NOT NULL,
  Name INT NOT NULL,
  Address INT NOT NULL,
  PRIMARY KEY (Code)
);

CREATE TABLE Branch
(
  Branch_ID INT NOT NULL,
  Name INT NOT NULL,
  Address INT NOT NULL,
  PRIMARY KEY (Branch_ID)
);

CREATE TABLE Loan
(
  Loan_ID INT NOT NULL,
  Loan_Type INT NOT NULL,
  Amount INT NOT NULL,
  PRIMARY KEY (Loan_ID),
  UNIQUE (Loan_Type)
);

CREATE TABLE Account
(
  Account_No INT NOT NULL,
  Account_Type INT NOT NULL,
  Balance INT NOT NULL,
  PRIMARY KEY (Account_No)
);

CREATE TABLE Customer
(
  Address INT NOT NULL,
  Phone INT NOT NULL,
  Name INT NOT NULL,
  Customer_ID INT NOT NULL
);
```
## RESULT: 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>

# EXP NO 1: ER DIAGRAM CREATION, RELATIONAL MODEL AND SCHEMA GENERATION  
### DATE
## AIM:
<div align="justify">
   To create a ER Diagram for Bank management system or College management system using ERD Plus tool and generate the relational model with schema. 
</div>

## Algorithm
1. Create a login with https://erdplus.com.
2. Create a new ER Diagram with name
3. Create a strong entity, relation and attributes.
4. Create a weak entity, relation and attributes.
5. Specify attributes unique, multivalued and composite attributes.

### ER Diagram 
![312316770-ade97f64-b5a6-4caf-b938-c39ae1434ea7](https://github.com/chandru0006r/DBMS/assets/99141707/31de5c3c-cbfe-477f-ab00-b641c451f68b)

### Relational model
![312316792-e13b0fc5-485a-4d8d-906a-f06650a30eed](https://github.com/chandru0006r/DBMS/assets/99141707/6f83fc1b-0ea1-4047-aad8-52d477e35b6e)

### SQL DDL Schema 
```
CREATE TABLE BANK
(
  Code INT NOT NULL,
  Name VARCHAR(100) NOT NULL,
  Addr VARCHAR(255) NOT NULL,
  PRIMARY KEY (Code)
);

CREATE TABLE BANK_BRANCH
(
  Branch_no INT NOT NULL,
  Addr VARCHAR(255) NOT NULL, 
  PRIMARY KEY (Branch_no)
);

CREATE TABLE LOAN
(
  Loan_no INT NOT NULL,
  Amount DECIMAL(10, 2) NOT NULL,
  Type VARCHAR(50) NOT NULL, 
  PRIMARY KEY (Loan_no)
);

CREATE TABLE CUSTOMER
(
  Phone VARCHAR(20) NOT NULL,
  Ssn INT NOT NULL,
  Name VARCHAR(100) NOT NULL,
  Addr VARCHAR(255) NOT NULL, 
  PRIMARY KEY (Ssn)
);

CREATE TABLE ACCOUNT
(
  Acct_no INT NOT NULL,
  Balance DECIMAL(10, 2) NOT NULL,
  Type VARCHAR(50) NOT NULL, 
  PRIMARY KEY (Acct_no)
);
```
## RESULT 
<div align="justify">
Thus the ER diagram was drawn and relational diagram, SQL DDL staements are generated using ERD plus tool.
</div>

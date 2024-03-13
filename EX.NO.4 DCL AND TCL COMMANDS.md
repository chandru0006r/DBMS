# EX.NO 4 Data Control Language (DCL) Commands and Transaction Control Languages (TCL) in SQL
### DATE:
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## Data Control Language (DCL) commands
* Data control language (DCL) is used to access the stored data.
* It is mainly used for revoke and to grant the user the required access to a database.
## List of DCL commands: 
1. GRANT : It is used to insert data into a table.
2. REVOKE: It is used to update existing data within a table.
## Transaction control language(TCL) commands
1. COMMIT : COMMIT command in SQL is used to save all the transaction-related changes permanently to the disk
2. START TRANSACTION : to start the transaction
3. ROLLBACK : undo the transaction upto savepoint 
4. SAVEPOINT : create a savepoint to save the different parts of the same transaction using different names

### Q1) Create a table employee with employee id ,name and Address

### QUERY:
```
CREATE TABLE employee (
    employee_id INT PRIMARY KEY,
    name VARCHAR(50),
    address VARCHAR(100)
);
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/e629d237-471e-4cf3-91c6-a6f1a279931e)


### Q2) Insert three rows into emploee table 


### QUERY:
```
INSERT INTO employee (employee_id, name, address)
VALUES (1, 'John Doe', '123 Main Street');

INSERT INTO employee (employee_id, name, address)
VALUES (2, 'Jane Smith', '456 Oak Avenue');

INSERT INTO employee (employee_id, name, address)
VALUES (3, 'Bob Johnson', '789 Pine Road');
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/f0d3ebde-15f0-418a-8c58-bf407f3a7d8c)


### Q3) Start the transaction and create a save point s1.

### QUERY:
```
BEGIN TRANSACTION;
SAVEPOINT s1;
```

### Q4) Perform insertion into employee table.

### QUERY:
```
INSERT INTO employee (employee_id, name, address)
VALUES (4, 'Alice Johnson', '101 Maple Lane');
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/c16ba352-1077-425c-bd5b-2829c97e2f9d)


### Q6)	Display the employee table and create a save point s2 .


### QUERY:
```
SAVEPOINT s2;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/c16ba352-1077-425c-bd5b-2829c97e2f9d)

### Q7)	Perform updation on any one of the row.


### QUERY:
```
UPDATE employee
SET address = 'New Address'
WHERE employee_id = 4;

```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/77236aa9-7dde-43c4-9edc-2ee19ae3ab10)



### Q8) Display the employee table and rollback to  save point s2 


### QUERY:
```
ROLLBACK TO s2;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/7a9041ac-f196-4d51-b32e-88b34f2c4f31)


### Q9) Display the employee table and commit the changes; 


### QUERY:
```
SELECT * FROM employee;
COMMIT;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/6cfcf4ed-8ea9-4aa4-9f38-20e0188c20f8)


### Q10) Rollback to save point s1;


### QUERY:
```
ROLLBACK TO s1;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/835b1a0d-1bc9-4e96-8794-827e7c7ae51d)


### Q11)	Create a new user and grant access to any one database with "insert and update"


### QUERY:
```
CREATE USER 'new_user'@'localhost' IDENTIFIED BY '1234';
GRANT INSERT, UPDATE ON your_database.* TO 'new_user'@'localhost';
FLUSH PRIVILEGES;
```

### OUTPUT:


### Q12) Check the user access and display the result 


### QUERY:
```
SHOW GRANTS FOR 'new_user'@'localhost';
SELECT * FROM mysql.user WHERE User = 'new_user' AND Host = 'localhost';
```

### OUTPUT:

### Q13) Revoke the privillages.

### QUERY:
```
REVOKE INSERT, UPDATE ON your_database.* FROM 'new_user'@'localhost';
FLUSH PRIVILEGES;
```

### OUTPUT:


## RESULT :
Thus the basic TCL and DCL commands are executed.

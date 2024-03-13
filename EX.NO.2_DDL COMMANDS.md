# EXP NO 2: DATA DEFINITION LANGUGE COMMANDS 
### DATE
## AIM:
To create a student database and execute DDL queries using SQL.


## THEORY
### DDL (Data Definition Language)

* DDL or Data Definition Language actually consists of the SQL commands that can be used to define the database schema.
* It simply deals with descriptions of the database schema and is used to create and modify the structure of database objects in the database.
* DDL is a set of SQL commands used to create, modify, and delete database structures but not data.
* These commands are normally not used by a general user, who should be accessing the database via an application.

 
### List of DDL commands: 
1. CREATE: This command is used to create the database or its objects (like table, index, function, views, store procedure, and triggers).
2. DROP: This command is used to delete objects from the database.
3. ALTER: This is used to alter the structure of the database.
4. TRUNCATE: This is used to remove all records from a table, including all spaces allocated for the records are removed.
5. RENAME: This is used to rename an object existing in the database.

## Query:
### 1) Create a database studentdb

### SQL QUERY:
```
CREATE TABLE Employee (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    DateOfBirth DATE,
    DepartmentID INT,
    Salary DECIMAL(10, 2)
);
```

### OUTPUT:
![Screenshot 2024-03-13 102150](https://github.com/paulsamson18/DBMS/assets/119405794/84b85426-ae71-4bb8-926b-ede816aac5a4)


### 2) Create a table student  and insert any two rows with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
```
INSERT INTO Employee (EmployeeID, FirstName, LastName, DateOfBirth, DepartmentID, Salary)
VALUES
    (1, 'John', 'Doe', '1990-05-15', 101, 60000.00),
    (2, 'Jane', 'Smith', '1985-08-23', 102, 75000.50),
    (3, 'Bob', 'Johnson', '1992-11-10', 101, 55000.75),
    (4, 'Alice', 'Williams', '1988-03-02', 103, 80000.25),
    (5, 'Charlie', 'Brown', '1995-07-18', 102, 70000.00);
```

### OUTPUT:
![Screenshot 2024-03-13 102014](https://github.com/paulsamson18/DBMS/assets/119405794/3d4ca759-647f-4303-9838-7f6902e01087)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY:
```
ALTER TABLE Employee ADD dept_name VARCHAR(50);
```

### OUTPUT:
![Screenshot 2024-03-13 102403](https://github.com/paulsamson18/DBMS/assets/119405794/2afb5937-a017-460a-812e-600be90fb639)

### 4) Rename the student table to mystudent

### SQL QUERY: 
```
ALTER TABLE old_table_name
RENAME TO new_table_name;
```

### OUTPUT:
![Screenshot 2024-03-13 102607](https://github.com/paulsamson18/DBMS/assets/119405794/6cd8ef6a-e541-4d7f-ac85-a8d4bcbaf922)


### 5) Delete the mystudent rows using truncate keyword

### SQL QUERY: 
```
TRUNCATE TABLE New_table_of_employess;
```
### OUTPUT:

### 4) Drop the mystudent table
 
### SQL QUERY: 
```
DROP TABLE New_table_of_employess;
```

### OUTPUT:

![image](https://github.com/paulsamson18/DBMS/assets/119405794/673f1d05-e5fd-48bd-8bc7-d331364340f6)







## Result:
         Thus the basic DDL commands in SQL are executed. 



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
CREATE TABLE student (
    RegisterNumber INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Address VARCHAR(100),
    PhoneNumber VARCHAR(15)
);
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/572f80a1-7e74-40e1-81ce-98a2a5f3d41f)


### 2) Create a table student  and insert any two rows with the following fieds RegisterNumber,Name,Age,Address,Phone number

### SQL QUERY: 
```
INSERT INTO student (RegisterNumber, Name, Age, Address, PhoneNumber)
VALUES (1001, 'Alice Johnson', 21, '789 Oak St, Villagetown', '555-123-4567');

INSERT INTO student (RegisterNumber, Name, Age, Address, PhoneNumber)
VALUES (1002, 'Bob Smith', 23, '321 Pine St, Hamletville', '555-987-6543');
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/bcd91279-b94e-428e-9977-da6a74775a1a)

### 3) Alter the above student table by adding another attribute department

### SQL QUERY:
```
ALTER TABLE student ADD COLUMN Department VARCHAR(50);
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/01356e82-5c60-4869-90ab-f21efc5cf583)

### 4) Rename the student table to mystudent

### SQL QUERY: 
```
ALTER TABLE student RENAME TO mystudent;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/02292ddd-9402-458d-a286-0add8a9c7eeb)


### 5) Delete the mystudent rows using truncate keyword

### SQL QUERY: 
```
TRUNCATE TABLE mystudent;
```
### OUTPUT:

### 4) Drop the mystudent table
 
### SQL QUERY: 
```
DROP TABLE mystudent;
```

### OUTPUT:

![image](https://github.com/chandru0006r/DBMS/assets/99141707/547320ca-5d44-4a2a-9558-faa6615b347c)







## Result:
         Thus the basic DDL commands in SQL are executed. 



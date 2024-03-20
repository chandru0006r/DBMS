# EX.NO.6 SubQueries, Views and Joins 
### DATE
## AIM
### To use SubQueries, Views and Joins in SQL 
## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```
## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'SCOTT', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-RR'), 3000, 20, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7934, 'MILLER', 'CLERK', 7782, TO_DATE('23-JAN-82', 'DD-MON-RR'), 1300, 10, 10);
```

## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```
## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```

### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.


### QUERY:
```
SELECT ENAME FROM EMP WHERE SAL > (SELECT SAL FROM EMP WHERE EMPNO = 7566);

```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/daaab3ab-99b3-4bf8-9add-be67bf097cf0)


### Q2) List the ename,job,sal of the employee who get minimum salary in the company.

### QUERY:
```
SELECT ENAME, JOB, SAL FROM EMP WHERE SAL = (SELECT MIN(SAL) FROM EMP);

```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/41757df4-249b-4694-bbd2-fa3a9c9233b5)


### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:
```
SELECT ENAME, JOB FROM EMP WHERE DEPTNO = 10 AND JOB IN (SELECT JOB FROM EMP WHERE DEPTNO = 30);
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/61b5db58-132e-4049-92cd-c45825ac4b10)


### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:
```
CREATE VIEW empv5 AS SELECT EMPNO, ENAME, JOB FROM EMP WHERE DEPTNO = 10;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/7b494a82-a6b9-485c-84d7-1e3f01d358be)


### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:
```
CREATE VIEW empv30 AS SELECT EMPNO, ENAME, SAL AS "SALARY" FROM EMP WHERE DEPTNO = 30;
SELECT * FROM empv30;

```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/a7ff478b-1391-4872-929c-b20116881177)

### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:
```
UPDATE EMP SET SAL = SAL * 1.1 WHERE JOB = 'CLERK';
```
![image](https://github.com/chandru0006r/DBMS/assets/99141707/6054e016-5725-46fd-9d1b-2876076cfef8)
![image](https://github.com/chandru0006r/DBMS/assets/99141707/29896cd2-ffcc-4a0f-bee8-01a83048d838)


### OUTPUT:

## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```
## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick Rimando', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad Davis', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham Zusi', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian Green', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Fabian Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geoff Cameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jozy Altidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brad Guzan', 'London', NULL, 5005);
```
## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```
## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'James Hoog', 'New York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nail Knite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pit Alex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mc Lyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paul Adam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauson Hen', 'San Jose', 0.12);
```
### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

### QUERY:
```
SELECT S.name AS Salesman, C.cust_name, C.city FROM Salesman1 S JOIN Customer1 C ON S.city = C.city;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/e0af30b8-03d2-48f3-b5ca-da47c5fd10ea)


### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.


### QUERY:
```
SELECT C.cust_name AS "Customer Name", C.city AS "Customer City", S.name AS "Salesman", S.commission AS "Commission"
FROM Customer1 C JOIN Salesman1 S ON C.salesman_id = S.salesman_id
WHERE S.commission > 0.13;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/d6f9fdaf-06c5-4283-9b05-c7d0c2363bb0)


### Q9) Perform Natural join on both tables

### QUERY:
```
SELECT * FROM Customer1 NATURAL JOIN Salesman1;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/991381c1-3afe-40e6-837c-b04b3fb817c5)


### Q10) Perform Left and right join on both tables

### QUERY:
```
SELECT * FROM Customer1 LEFT JOIN Salesman1 ON Customer1.salesman_id = Salesman1.salesman_id;
SELECT * FROM Customer1 RIGHT JOIN Salesman1 ON Customer1.salesman_id = Salesman1.salesman_id;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/e0648f21-b56c-44bd-99d0-2d05d854bfbb)
![image](https://github.com/chandru0006r/DBMS/assets/99141707/93fe2d76-53b3-4fd4-ab2c-c348d7795641)


## RESULT 
### Thus the basics of subqueries,views,joins are performed in SQL.

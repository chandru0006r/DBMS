# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.

# THEORY
## DML(Data Manipulation Language)
*  The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements.
*  It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

## List of DML commands: 
1. INSERT: It is used to insert data into a table.
2. UPDATE: It is used to update existing data within a table.
3. DELETE: It is used to delete records from a database table.
4. SELECT: The SELECT command shows the records of the specified table.

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
UPDATE manager
SET salary = salary + (salary * 0.1),
    annualsalary = annualsalary + (annualsalary * 0.1),
    commission = commission + (commission * 0.1);
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/8a0cc7ce-2814-430c-8970-d8a01fe405be)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
DELETE FROM manager
WHERE salary < 2750;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/514780f5-4ac0-4faa-a597-ea6f09c5eca5)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
SELECT ename AS "Name", salary * 12 AS "Annual Salary"
FROM manager;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/7f0602b2-b993-4e41-a5ad-9bae99ad87af)


### Q5)	List the names of Clerks from emp table.


### QUERY:
```
SELECT ename
FROM manager
WHERE designation = 'clerk';
```
### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/ef08df12-078c-4b9b-bf85-920dd2ed8c2f)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```
SELECT ename
FROM manager
WHERE designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/822fda18-cd7a-4623-ac7a-536a80c54794)


### Q7)	List the names of employees not eligible for commission.

### QUERY:
```
SELECT ename
FROM manager
WHERE commission IS NULL;
```
### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/8da55019-72ca-461e-826d-c4b9f55945e3)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
SELECT ename
FROM manager
WHERE ename LIKE 's%' OR ename LIKE '%s';
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/12c0321c-2f2d-45b6-bee2-de23e1a490ca)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
SELECT ename, designation AS job, deptno, Hiredate
FROM manager
ORDER BY Hiredate ASC;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/e0b2079e-fe17-49d7-bbeb-38225cab2f6a)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
SELECT *
FROM manager
WHERE Hiredate < TO_DATE('30-Sep-81', 'DD-Mon-YY');
```


### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/447ffe13-6422-4bb6-a646-e958e72e6e42)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
SELECT ename, deptno, salary AS sal
FROM manager
ORDER BY deptno ASC, salary DESC;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/9545b0d5-6e7e-4442-a451-01031b5a76ed)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
SELECT ename
FROM manager
WHERE deptno NOT IN (30, 40, 10);

```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/1bbb825c-e2e2-437a-ace7-1cb93d996d8a)


### Q13) Find number of rows in the table EMP

### QUERY:
```
SELECT COUNT(*) AS num_rows
FROM manager;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/8b97d908-f08c-4621-bbac-261dcf9c8505)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
SELECT MAX(salary) AS max_salary, MIN(salary) AS min_salary, AVG(salary) AS avg_salary
FROM manager;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/439a91d4-d7c1-46e3-933d-5a5f7d5b8a23)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees
FROM manager
GROUP BY designation
ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/chandru0006r/DBMS/assets/99141707/a169b468-8e12-45c9-aa60-ce7b4a70553c)


## RESULT :
Thus the basic DML commands are executed.

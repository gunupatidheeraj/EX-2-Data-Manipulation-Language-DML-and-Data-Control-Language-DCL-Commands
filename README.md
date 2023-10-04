# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL

## AIM:
To create a manager database and execute DML queries using SQL.

## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table managers(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into managers values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into managers values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into managers values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into managers values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
### Output:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/0e782e57-ce30-4fbe-940e-fa041443a8bb)

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update managers set salary=salary+(salary*10/100);
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/e4effb28-818f-494b-9f5d-1427da218118)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete managers where salary<2750;
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/727b6d4a-c7e4-4cb2-a0b3-edcc9c33cfdc)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```SELECT
ename AS "Name",
salary*12 AS "Annual Salary"
FROM
managers;
```
### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/af8e963c-37f8-4581-af1e-9f489f9f4dd6)

### Q4)	List the names of Clerks from emp table.


### QUERY:
```
select ename from managers where designation='clerk';
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/9ee4efa9-0a2f-46d2-b3f7-b3352ae25c1e)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```
select ename from managers where designation!='manager';
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/9f29bbfe-bbbe-4681-9c32-fbd7344c122a)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from managers where commission=0;
```

### OUTPUT:

![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/0c354b05-fc19-48a6-bfef-78a3cfaddc83)


### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/7110931d-a370-4a85-9231-c6de2c10f4a3)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/80bf3aeb-0bbe-42aa-b5ad-e746e7c872b3)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from managers where hiredate < '30 SEP 81';
```

### OUTPUT:

![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/5f76021f-fc97-4b30-9e07-26b0a3aa7858)

### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```

### OUTPUT:

![Listing](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/507318c9-f9ea-44ec-bcae-57a47c7bce5b)

### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/65d9a1c8-5aef-412b-b901-b3e7ec50a9a1)


### Q12) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from managers;
```
### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/435f9545-715a-4bf3-8b29-6ad269fcf0ee)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary)
as averagesal from managers;
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/11952b4a-4e56-4769-9b8f-d2cfa9a8b6fa)


### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```

### OUTPUT:
![image](https://github.com/SudharsanamRK/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/115523484/1f367903-3f20-4167-860c-9003f024688a)

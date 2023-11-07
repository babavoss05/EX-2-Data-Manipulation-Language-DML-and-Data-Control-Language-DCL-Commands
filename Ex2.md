# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## DATE: 11/8/23
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
update manager set salary=salary+(salary*0.10);


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/0fef720f-5309-4de8-9f7c-3fc8cc6040d1)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY: 
delete from manager where salary<2750;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/da1fd1b6-9447-487b-b8ab-59d2e43a7cbd)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY: 
select ename as "Name",salary*12 as "Annual salary" from manager;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/8a452079-2698-4dcf-a33c-e347f51cd4ff)


### Q5)	List the names of Clerks from emp table.


### QUERY: 
select ename from manager where designation='clerk';


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/6b3c0017-cb39-42c5-9a7d-854920b1f2d6)



### Q6)	
List the names of employee who are not Managers.


### QUERY: 
select ename from manager where designation <> 'manager';


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/705eb94f-5d8c-4006-8e15-1cc159076d43)



### Q7)	List the names of employees not eligible for commission.


### QUERY: 
select ename from manager where commission=0;


### OUTPUT: 
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/6b8ba5d7-6c8d-44bd-9171-ff1d244f9e46)



### Q8)	List employees whose name either start or end with ‘s’.


### QUERY: 
select ename from manager where ename like '%S' or ename like 'S%';


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/aad65f19-cd12-4db4-ad9c-2f11c8a98f04)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

 
### QUERY: 
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/79b8e592-4b84-49c0-a880-956cb779e2ef)



### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY: 
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');


### OUTPUT:

![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/e36efe21-9b69-4141-9477-903c3636d08f)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY: 
select ename,deptno,salary from manager order by deptno asc,salary desc;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/c7d274ef-6a31-4ba0-ad1a-852c868d9d9b)



### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY: 
select ename from manager where deptno not in (30,40,10);


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/785423d5-bac1-4930-b047-23d35d1352ea)


### Q13) Find number of rows in the table EMP

### QUERY: 
select count(*) from manager;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/98c5ca3c-58d9-4407-bf57-b8d2a6d38e6b)



### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY: 
select max(salary) from manager;
select min(salary) from manager;
select avg(salary) from manager;


### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/1f586d4a-d95e-4632-992c-bbaddc5e162f)



### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;



### OUTPUT:
![image](https://github.com/dineshgl/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/103019882/78f2fc17-cd94-446d-bee6-5a8bd5f79519)


## RESULT:
   Manager database was created and DML queries were executed.

# DatabaseTesting
DQL-Select</br>
DDL-create,alter,drop,rename,truncate</br>
DML-updat,insert,delete</br>
DCL-grant,revoke</br>
TCL-commit,savepoint,rollback</br>

#### 1)Display table in proper format
set  lines 200 <br>
 set pages 200<br>

#### 2)select employee with deptno 10,20
select *  from emp where deptno in(10,20);
#### 3)select employee with  salary between 2000 and 3000
select sal from emp between 2000 and 3000;
#### 4)select distinct deptno
select distinct deptno from emp;
#### 5) select  total no of records and total depts 
select count(*) , count(deptno) from emp;
#### 6) find max sal by dept  having sal greater than 3000
select max(sal) from emp</br>
group by job</br>
having max(sal)>3000


#### 7)deptno having more than 4 employees
select deptno from emp</br>
Group by deptno</br>
having count(*) >4

#### 8)Create table products
Create Table Products </br>
(ProdId Number(4) Primary key, </br>
ProdName Varchar(10) Not Null, </br>
Qty Number(3) Check(qty>0) </br>
);

#### 9)find all tables
Select * from tab;

#### 10)add  column model_no in products table
Alter table products </br>
Add model_no varchar(10) Not NULL;

#### 11)show structure of table
Desc products;
#### 12)create row
insert into products </br>
Values(1,’laptop’,4,23);	

#### 13)update row value
Update emp </br>
Set sal=sal+200 </br>
Where empno=7302;

#### 14)delete a value
delete from products where prodid=2;

#### 15)roll back has no effect after commit

#### 16) select 3rd highest salary
select * from emp a </br>
where 2=(select count(distinct(b.sal)) from emp b </br>
where a.sal < b.sal);

#### 17)bottom 3 salaries
select * from emp a </br>
where 2>=(select count(distinct(b.sal)) from emp b </br>
where a.sal > b.sal);

#### 18)top(highest) 3 salaries
select * from emp a </br>
where 2>=(select count(distinct(b.sal)) from emp b </br>
where a.sal < b.sal);

#### 19) display top 2 records
Select *  from emp </br>
Where  rownum <=2;


#### 20) Finds any values that have "e" in any position
select * from emp 
WHERE ename LIKE '%e%'  ;

### Joins
#### 1)inner join
select a.ename , b.dname </br>
From emp a , dept b </br>
Where a.deptno=b.deptno; </br>
-------------------------------------------- </br>
SELECT emp.ename , dept.dname </br>
FROM emp </br>
INNER JOIN dept </br>
ON emp.deptno= dept.deptno; </br>

#### 2)right outer join
select a.ename , b.dname </br>
From emp a , dept b </br>
Where a.deptno(+)=b.deptno;

-------------------------------------------- </br>
SELECT emp.ename , dept.dname </br>
FROM emp </br>
RIGHT OUTER JOIN dept ON emp.deptno= dept.deptno;

#### 3) left outer join
select a.ename , b.dname </br>
From emp a , dept b </br>
Where a.deptno=b.deptno(+);

#### 4)self join(emp with their manager name)
select a.ename "empname",b.ename "mgrname" </br>
from emp a ,emp b </br>
where a.mgr=b.empno;

#### 5)3 table join
select a.ename, b. loc, c.clerkname </br>
from emp a, dept b ,deptclerk c </br>
where a.deptno=b.deptno </br>
and b.loc=c.loc

![capture](https://user-images.githubusercontent.com/24494133/51387929-ddda1700-1b4d-11e9-9551-f607e35bef14.PNG)

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

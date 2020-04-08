## 一、where
```sql
select*from t_employee WHERE sal>(select sal from t_employee WHERE ename='SMITH');
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/3.1.png)
query
```sql
select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.Hiredate,t1.sal,t1.comm
from t_employee t1 inner join t_employee t2
on t1.sal>t2.sal and (t2.ename='SMITH');
select * from t_employee;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/3.2.png)
## 二、where
```sql
select*from t_employee WHERE (sal, job)=(select sal,job from t_employee where ename='smith');
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/3.3.png)
query
```sql
select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.Hiredate,t1.sal,t1.comm from t_employee t1 inner join t_employee t2 on 
(t1.sal = t2.sal and (t2.ename='SMITH')) AND (t1.job=t2.job and (t2.ename='SMITH'));
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/3.4.png)

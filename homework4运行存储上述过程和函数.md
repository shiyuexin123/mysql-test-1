## 一、创建存储过程
```sql
SELECT * FROM t_employee;
DELIMITER $$ 
CREATE PROCEDURE proce_employee_sal1 () 
BEGIN
SELECT sal
FROM t_employee2;
END$$
DELIMITER ;
CALL proce_employee_sal1();
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/4.1.png)
## 二、创建函数
```sql
SELECT * FROM t_employee;
DELIMITER $$
CREATE FUNCTION func_employee_sal (empno INT)   
RETURNS DOUBLE
BEGIN
RETURN (SELECT sal 
FROM t_employee 
WHERE t_employee.empno = empno);
END$$
DELIMITER ;

SELECT func_employee_sal(7369);
SELECT func_employee_sal(7934);
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/4.2.png)

![](https://github.com/shiyuexin123/mysql-test-1/blob/master/4.3.png)

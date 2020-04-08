姓名：施跃鑫  学号：17061522
## 一、介绍对数据库操作相关的命令
1、创建一个新的数据库
```sql
CREATE DATABASE ONE;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.1.png)
2、查看和选择数据库
```sql
SHOW DATABASES;  
USE ONE;          
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.2.png)
3、删除数据库
```sql
DROP　DATABASE ONE；
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.3.png)
## 二、如何查看MySQL数据库中的存储引擎
1、查看所支持的存储引擎
```sql
SHOW ENGINGS;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.4.png)
2、查看默认的存储引擎
```sql
SHOW VARIABLES LIKE ‘%storage_engine%’;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.5.png)
## 三、介绍对表操作的相关命令
1、在数据库中创建一个新的表
```sql
CREATE TABLE t_dept(
deptno INT,
dname VARCHAR（20），
loc VARCHAR(40)
);
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.6.png)
2、查看表的定义信息
```sql
DESCRIBE(DESC) t_dept;	
SHOW CREATE TABLE t_dept; 	 
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.7.png)
3、删除表
```sql
DROP TABLE t_dept;	
DESCRIBE t_dept;      
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.8.png)
4、修改表名
```sql
ALTER TABLE t_dept RENAME t_dept1;  
SHOW TABLES;	
DESC t_dept;	
DESC t_dept1;	
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.9.png)
5、增加字段和删除字段
1）在表的最后面增加字段
```sql
DESC t_dept1;		
ALTER TABLE t_dept1 ADD Tel VARCHAR(20);
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.10.png)
2）在表的最前面增加字段
```sql
DESC t_dept1;
ALTER TABLE t_dept1 ADD aname VARCHAR(10) FIRST； 
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.11.png)
3）在表指定字段后增加字段
```sql
DESC t_dept1;
ALTER TABLE t_dept1 ADD bname VARCHAR(10) AFTER dname; 
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.12.png)
4)删除字段
```sql
DESC t_dept1;
ALTER TABLE t_dept1 DROP bname; 
ALTER TABLE t_dept1 DROP dname;
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.13.png)
6.修改字段
1）修改字段的数据类型
```sql
DESC t_dept1; 
ALTER TABLE t_dept1 MODIFY Tel INT; 
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.14.png)
2）同时修改字段的名字和数据类型
```sql
DESC t_dept1; 
ALTER TABLE t_dept1 CHANGE
 aname Dname VARCHAR(10); 
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.15.png)
3）修改字段顺序
```sql
DESC t_dept1; 
ALTER TABLE t_dept1 
		MODIFY  deptno INT(11) AFTER loc; 
DESC t_dept1;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.16.png)
## 四、操作表的约束
```sql
CREATE TABLE two(
deptno INT NOT NULL, 
aname VARCHAR(20) DEFAULT 'Petter', 
Bname VARCHAR(20) UNIQUE, 
loc VARCHAR(40),
number INT PRIMARY KEY AUTO_INCREMENT
);
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.17.png)
## 五、数据的操作
1、插入数据记录
```sql
create table list(
name VARCHAR(20),
sex VARCHAR(20),
tel INT,
local VARCHAR(20)
);
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.18.png)
```sql
INSERT INTO list(name,sex,tel,local)
VALUES("Baby","female",8208820,"ZheJiang"); 
SELECT*FROM LIST; 
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.19.png)
2.同时插入多条数据记录
```sql
INSERT INTO list(name,sex,tel,local)
VALUES("Bob","man",1538482,"NanJing"),
("CaiXUkun","Female",1564812,"ShangHai"),
("XiaoZhan","man",1156212,"ShanXi"),
("LuHan","Female",1535842,"HuNan");
SELECT*FROM LIST; 
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.20.png)
3、将一个表的记录插入另一个表中
```sql
CREATE TABLE LIST2(
TNAME VARCHAR(20),
TSEX VARCHAR(10),
TTEL INT,
TLOCAL VARCHAR(20)
);
DESC LIST2;
INSERT INTO list2(TNAME,TSEX,TTEL,TLOCAL)
VALUES("KangKang","Man",34564814,"ChongQing"),
("XinXin","Man",45416426,"ZheJiang"),
("HuiHui","Man",12515364,"ZheJiang"),
("QiQi","Female",83466468,"GuangXi");
INSERT INTO list(name,sex,tel,local)
SELECT TNAME,TSEX,TTEL,TLOCAL FROM LIST2;
SELECT*FROM LIST;
code here
```
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.21.png)
![](https://github.com/shiyuexin123/mysql-test-1/blob/master/1.22.png)

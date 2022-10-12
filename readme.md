# mysql初级

面试题预览

![image-20221012094908001](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012094908001.png)

大纲

![image-20221012095127088](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012095127088.png)





## 1.基础篇

###  1.1 MYSQL概述

####  1.1.1 数据库相关概念

![image-20221012095705273](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012095705273.png)

####  1.1.2 MYSQL安装

参见https://gitee.com/woldier/docker#31-mysql%E9%83%A8%E7%BD%B2

![image-20221012101943736](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012101943736.png)

####  1.1.3 数据模型

数据库,表

### 1.2 SQL

####  1.2.1 SQL通用

![image-20221012102629000](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012102629000.png)

#### 1.2.2 SQL分类

![image-20221012102732208](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012102732208.png)

####  1.2.3 DDL

- 数据库操作

![image-20221012103043932](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012103043932.png)

- 表操作

![image-20221012103353986](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012103353986.png)

![image-20221012103602859](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012103602859.png)



![image-20221012103650327](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012103650327.png)

![image-20221012103841864](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012103841864.png)

![image-20221012104032795](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012104032795.png)



案例

![image-20221012104236619](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012104236619.png)



- 表操作-修改

![image-20221012104421794](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012104421794.png)

```sql
alter table tablename add nickname varchar(20) comment '昵称';
```

![image-20221012104526763](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012104526763.png)

案例: 将emp表的nickname字段修改为username,类型为varchar(30)

```sql
alter table emp change nickname username varchar(30) comment '用户名';
```

![image-20221012104858082](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012104858082.png)

- 表操作删除

![image-20221012104937637](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012104937637.png)



#### 1.2.4 DML

![image-20221012105519145](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012105519145.png) 



#### 1.2.5 DQL

![image-20221012105956434](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012105956434.png)

![image-20221012110208497](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012110208497.png)

- 基本查询



- 条件查询(where)

![image-20221012111251694](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012111251694.png)

- 聚合函数(count,max,min,avg,sum)

  ![image-20221012111921189](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012111921189.png)

- 分组查询(group by)

  ![](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012112117176.png)

  ![image-20221012112441185](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012112441185.png)

  ![image-20221012112521635](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012112521635.png)

- 排序查询(order by)

![image-20221012112643671](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012112643671.png)

![image-20221012112815039](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012112815039.png)

- 分页查询(limit)

![image-20221012112923912](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012112923912.png)

案例练习

![image-20221012113112749](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012113112749.png)

```sql
-- 1
select * from emp where gender = '女' and age in(20,21,22,23) ;

--2 
select * from emp where gender = '男' and (age between 20 and 40 )and name like '___';

--3
select gender, count(*) from emp where age < 60 groupby gender;

--4
select name ,age  from emp where age <= 35  order by age ,entrydate desc;

--5 
select * from emp where gender = '男' and (age between 20 and 40) order by order by age ,entrydate  limit 5
```

- 执行顺序

![image-20221012143713471](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012143713471.png)

 

####  1.2.6 DCL

![image-20221012144154983](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012144154983.png)

- 管理用户

![image-20221012145336745](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012145336745.png)

```sql
-- 设置用户名,可连接的ip(%表示所有),密码(这是密码设置为password)
create user 'woldier'@'%' identified by 'password' ;

-- 修改用户密码
alter user 'wodlier'@'%' identified with mysql_native_password by 'newPassword';

```



- 权限控制

![image-20221012145834891](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012145834891.png)

![image-20221012145907875](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012145907875.png)

```sql
-- 查询权限
show grants for 'woldier'@'%';
-- 授予权限 为用户名为woldier的用户授予,名为woldierDB的数据库中所有表,所有权限
grant all on woldierDB.* to 'woldier'@'%';
--册小权限
revoke all on woldierDB.* from 'woldier'@'%'
```

![image-20221012150455397](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012150455397.png)



### 1.3 函数

![image-20221012151156890](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012151156890.png)

####  1.3.1 字符串函数

![image-20221012151408198](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012151408198.png)

```sql
-- 1
select concat('hello','world');
--2
select lower('Hello');
--3
select upper('hello');
--4
select lpad('11',5,'x');
--5
select rpad('11',5,'x');
--6
select trim(' Hello World   ');
--7 结果为Hello 索引从1开始 取左右闭区间
select substring('Hello World',1,5);
```

- 案例练习

![image-20221012151925933](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012151925933.png)

```sql
update emp set workno = lpad(wordkno,5,'0');
```

#### 1.3.2 数值函数

![image-20221012152136749](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012152136749.png)

```sql
--结果为2
select ceil(1.1); 
--结果为1
select floor(1.1)
--结果为3
select mod(3,4);
--0-1的随机数
select rand();
--round 四舍五入,结果为2.32
select round(2.323,2);
```

- 案例练习

![image-20221012152522088](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012152522088.png)

```sql
select round(rand()*100000,0);
--上面还有问题,不一定保证有六位2
select lpad(round(rand()*100000,0);,6,'0');

```



#### 1.3.3 日期函数

![image-20221012152845896](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012152845896.png)

```sql
select data_add(now(),interval 70 day);
select data_add(now(),interval 70 month);

select datediff('2021-10-01','2022-01-21');
```

- 案例

查询所有员工的入职天数,并且根据入职天数倒序排序

```sql
SELECT name,DATEDIFF(CURDATE(),entrydate) as 'days' FROM emp order by days desc
```



#### 1.3.4 流程函数

![image-20221012153743831](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012153743831.png)

```sql
select if(true,'OK','ERROR');
select if(true,'OK','ERROR');

select ifnull('OK','DEFAULT');
select ifnull('','DEFAULT'); -- 任然返回 ''
select ifnull('OK','DEFAULT'); -- 返回DEFAULT

-- 查询emp表的公告姓名及工作地址(北京上海则返回一线城市,否则返回二线城市)
select 
	name ,
	CASE workaddress WHEN '北京' THEN '一线城市' WHEN '上海' THEN '一线城市' ELSE '二线城市' END 
	from emp;  
```

- 案例

![image-20221012154520563](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012154520563.png)

```sql
select 
	name,
	(CASE  WHEN score>=85 then '优秀' when　score >=60 THEN '及格' ELSE '不及格' end) as '成绩'
	from student
```

### 1.4 约束

#### 1.4.1 概述

![image-20221012155413321](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012155413321.png)

注意:约束是作用于表中字段上的,可以在从创建表/修改表的时候添加约束.

#### 1.4.2 约束演示

![image-20221012160138716](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012160138716.png)

```sql
create table user(
    id int primary key autp_increment commont '主键';
    name varchar(10) not null unique commont '姓名';
    age int check (age>0 && age<= 120) commont '年龄';
    status char(1) default '1' commont '状态';
    gender char(1) commont '性别';
    
    
) comment '用户表'

```



####  1.4.3 外键约束

![image-20221012161029438](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012161029438.png)

![image-20221012161215982](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012161215982.png)

![image-20221012161424040](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012161424040.png) 

> #  删除更新行为

![image-20221012161553417](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012161553417.png)

![image-20221012161834170](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012161834170.png)

###  1.5 多表查询

####  1.5.1  概述

![image-20221012163049661](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012163049661.png)

- 一对多

![image-20221012163147115](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012163147115.png)

- 多对多

![image-20221012163222089](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012163222089.png)

- 一对一

![image-20221012163641554](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012163641554.png)

- 多表查询 

![image-20221012163952455](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012163952455.png)

- 多表查询的分类

  ![image-20221012164036737](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012164036737.png)



#### 1.5.2 内连接

![image-20221012165009444](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012165009444.png)

```sql
-- 查询每一个员工的姓名,及关联部门的名称
--表结构 emp,dept
-- 查询出两张表的交集部分,若emp中某员工的部门为null或者不在dept中,则该员工不会被查询出来
select * from emp, dept where emp.dept_id = dept.id;

select * from emp inner jion dept on emp.dept_id = dept.id;
```



#### 1.5.3 外连接

![image-20221012165734458](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012165734458.png)

```sql
-- 查询emp表的所有数据,和对应的部门信息(会查询到交集,及左表特有的)
select * from emp left outer jion dept on emp.dept_id = dept.id;
-- 查询dept表的所有数据,和对应的部门信息(会查询到交集,及右表特有的)
select * from emp right outer jion dept on emp.dept_id = dept.id;
```

#### 1.5.4 自连接

注:自连接中表必须使用别名

![image-20221012170855099](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012170855099.png)

```sql
--查询员工及其所属的领导
select a.name '员工' ,b.name '上司' from emp a,emp b where a.managerid = b.id
-- 查询所有员工emp及其领导的名字emp,如果没有领导也需要查询出来
select  a.name '员工' ,b.name '上司' from emp a left outer jion emp b on a.managerid = b.id
```

#### 1.5.5 联合查询union

 ![image-20221012172602554](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012172602554.png)

对于联合查询的多张表的类书必须保持一致,字段类型也需要保持一致

union all 会将全部的数据直接组合在一起,union会对合并后的数据去重

问:为什么不用or来实现相同的效果呢?

https://www.jianshu.com/p/cca9d65adc01

https://www.cnblogs.com/liangyongrui/p/8612081.html

```sql
-- 查询薪资低于5000的员工和年龄大于50岁的员工(不去重)
select * from emp where salary <5000 
union all
select * from emp where age<50;

-- 查询薪资低于5000的员工和年龄大于50岁的员工(去重)
select * from emp where salary <5000 
union 
select * from emp where age<50;
```



#### 1.5.6 子查询

![image-20221012173753537](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012173753537.png)

- 标量子查询

![image-20221012200138883](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012200138883.png)

```sql
--标量子查询
-- 1.查询"销售部"的所有员工信息
-- a.查询"销售部"部门id
select id from dept where name = '销售部';
-- b.根据销售部部门id,查询员工信息
select * from emp where dept_id = (select id from dept where name = '销售部');

--查询在"王五"之后入职的员工信息
-- a.查询"王五"的入职时间
select entrydate from emp where name ='王五';
-- b.根据查询到的日期信息筛选出在这之后入职的员工
select * from emp where entrydate > (select entrydate from emp where name ='王五');
```

- 列子查询

![image-20221012201211992](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012201211992.png)

```sql
-- 列子查询
-- 1.查询"销售部"和"市场部"的所有员工信息
-- a.查询"销售部"和"市场部"的部门id
select id from dept where name ='销售部' or name ='市场部';
-- b.根据部门id,查询员工信息
select * from emp where dept_id in (select id from dept where name ='销售部' or name ='市场部');


-- 2.查询比财务部所有人工资都高的员工信息
-- a.查询财务部所有员工的工资
select id from dept where name = '财务部';

select salary from emp where dept_id = (select id from dept where name = '财务部');
-- b.查询比所有财务部工资都高的员工的信息
SELECT * FROM emp WHERE salary > ALL(select salary from emp where dept_id = (select id from dept where name = '财务部'));

-- 3.查询比研发部任意一人工资都高的员工信息
-- a.查询研发部所有员工的工资
select salary from emp where dept_id = (select id from dept where name = '研发部');
-- b.查询比研发部任意一人工资都高的员工信息
select * from emp where salary > ANY (select salary from emp where dept_id = (select id from dept where name = '研发部'));
```



- 行子查询

![image-20221012202753187](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012202753187.png)

```sql
-- 1.查询与'张无忌'的薪资及直属领导相同的员工信息
-- a.张无忌工资与直属领导
select salary , managerid from emp where name = '张无忌';
-- b.查询与张无忌相同的员工信息
select * from emp where (salary,managerid) = (select salary , managerid from emp where name = '张无忌');
```



- 表子查询 

![image-20221012203328488](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012203328488.png)

```sql
-- 1.查询与'张三','李四'的职位和薪资相同的员工信息
-- a.查询张三,李四的薪资
select position,salary from emp where name ='张三' or name = '李四';
-- b.查询与'张三','李四'的职位和薪资相同的员工信息
select * from emp where (position,salary) = IN (select position,salary from emp where name ='张三' or name = '李四') 

-- 2. 查询入职日期是"2006-01-01"之后的员工信息,及其部门信息
-- a. 查询入职日期是"2006-01-01"之后的员工信息
select * from emp where entrydate > '2006-01-01';
-- b 查询这部分员工及其对于的部门信息
select * from (select * from emp where entrydate > '2006-01-01') e left jion dept d on
e.dept_id = d.id
```



- 练习

```sql
create table dept(
    id   int auto_increment comment 'ID' primary key,
    name varchar(50) not null comment '部门名称'
)comment '部门表';

create table emp(
    id  int auto_increment comment 'ID' primary key,
    name varchar(50) not null comment '姓名',
    age  int comment '年龄',
    job varchar(20) comment '职位',
    salary int comment '薪资',
    entrydate date comment '入职时间',
    managerid int comment '直属领导ID',
    dept_id int comment '部门ID'
)comment '员工表';
INSERT INTO dept (id, name) VALUES (1, '研发部'), (2, '市场部'),(3, '财务部'), (4, '销售部'), (5, '总经办'), (6, '人事部');
INSERT INTO emp (id, name, age, job,salary, entrydate, managerid, dept_id) VALUES
            (1, '金庸', 66, '总裁',20000, '2000-01-01', null,5),

            (2, '张无忌', 20, '项目经理',12500, '2005-12-05', 1,1),
            (3, '杨逍', 33, '开发', 8400,'2000-11-03', 2,1),
            (4, '韦一笑', 48, '开发',11000, '2002-02-05', 2,1),
            (5, '常遇春', 43, '开发',10500, '2004-09-07', 3,1),
            (6, '小昭', 19, '程序员鼓励师',6600, '2004-10-12', 2,1),

            (7, '灭绝', 60, '财务总监',8500, '2002-09-12', 1,3),
            (8, '周芷若', 19, '会计',48000, '2006-06-02', 7,3),
            (9, '丁敏君', 23, '出纳',5250, '2009-05-13', 7,3),

            (10, '赵敏', 20, '市场部总监',12500, '2004-10-12', 1,2),
            (11, '鹿杖客', 56, '职员',3750, '2006-10-03', 10,2),
            (12, '鹤笔翁', 19, '职员',3750, '2007-05-09', 10,2),
            (13, '方东白', 19, '职员',5500, '2009-02-12', 10,2),

            (14, '张三丰', 88, '销售总监',14000, '2004-10-12', 1,4),
            (15, '俞莲舟', 38, '销售',4600, '2004-10-12', 14,4),
            (16, '宋远桥', 40, '销售',4600, '2004-10-12', 14,4),
            (17, '陈友谅', 42, null,2000, '2011-10-12', 1,null);

create table salgrade(
    grade int,
    losal int,
    hisal int
) comment '薪资等级表';

insert into salgrade values (1,0,3000);
insert into salgrade values (2,3001,5000);
insert into salgrade values (3,5001,8000);
insert into salgrade values (4,8001,10000);
insert into salgrade values (5,10001,15000);
insert into salgrade values (6,15001,20000);
insert into salgrade values (7,20001,25000);
insert into salgrade values (8,25001,30000);
```



![image-20221012214909895](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221012214909895.png)

```sql
-- 1.查询员工的姓名,年龄,职位,部门信息
select e.name '姓名' ,e.age '年龄',e.job '职位',d.name '部门' from emp e LEFT JOIN dept d ON e.dept_id = d.id;

-- 2.查询年龄小于30岁的员工姓名,年龄,职位,部门信息
select e.name '姓名' ,e.age '年龄',e.job '职位',d.name '部门' from (select * from emp where age<30) e  LEFT JOIN dept d ON e.dept_id = d.id;

-- 3.查询拥有员工的部门id,部门名称
select dept_id from emp GROUP BY dept_id;
select a.dept_id,d.name '部门' from (select dept_id from emp GROUP BY dept_id) a LEFT JOIN dept d ON a.dept_id = d.id;

-- 4.查询所有年龄大于40岁的员工,及其归属的部门名称;如果员工没有分配部门,也需要显示出来

SELECT * from emp where age>40;

SELECT a.*,d.`name` from (SELECT * from emp where age>40) a LEFT JOIN dept d on a.dept_id = d.id;
-- 5.查询所有员工的工资等级

```


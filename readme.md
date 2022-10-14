-面试题预览

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
select a.`name` , b.grade  from emp a , salgrade b where (a.salary between b.losal and b.hisal);
-- 6.查询'研发部'所有员工所有信息及工资等级

select e.* from emp e,dept d where e.dept_id = d.id and d.`name`='研发部' 

SELECT a.*,b.grade '等级' FROM (select e.* from emp e,dept d where e.dept_id = d.id and d.`name`='研发部' ) a, salgrade b where (a.salary between b.losal and b.hisal);
-- 7.查询'研发部'员工的平均工资
SELECT AVG(e.salary) '工资' from emp e ,dept d where e.dept_id = d.id and d.`name` = '研发部'
-- 8.查询工资比 灭绝 高的员工信息
select * from emp where salary > (SELECT salary from emp where `name`='灭绝');
-- 9.查询比平均薪资高的员工信息
select * from emp where salary >(SELECT avg(salary) from emp);

-- 10.查询低于本部门平均薪资的员工人数
SELECT dept_id,avg(salary) 'salary' from emp  GROUP BY dept_id;

SELECT a.* from emp a, (SELECT dept_id,avg(salary) 'salary' from emp  GROUP BY dept_id) b where a.dept_id = b.dept_id and a.salary<b.salary

-- 11.查询所有的部门信息,并且统计部门员工人数
SELECT a.*,d.`name` from (SELECT dept_id,count(*) '人数' from emp GROUP BY dept_id) a left JOIN dept d on a.dept_id = d.id;
```



###  1.6 事务

#### 1.6.1 事务简介

![image-20221013092127902](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013092127902.png)

#### 1.6.2 事务操作

- 数据准备

```sql
-- ---------------------------- 事务操作 ----------------------------
-- 数据准备
create table account(
    id int auto_increment primary key comment '主键ID',
    name varchar(10) comment '姓名',
    money int comment '余额'
) comment '账户表';
insert into account(id, name, money) VALUES (null,'张三',2000),(null,'李四',2000);

-- 恢复数据
update account set money = 2000 where name = '张三' or name = '李四';
```

```sql

-- 转账操作 (张三给李四转账1000)
-- 1. 查询张三账户余额
select * from account where name = '张三';

-- 2. 将张三账户余额-1000
update account set money = money - 1000 where name = '张三';

模拟程序执行报错 ...

-- 3. 将李四账户余额+1000
update account set money = money + 1000 where name = '李四';

```

![image-20221013093013651](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013093013651.png)

![image-20221013093350269](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013093350269.png)





#### 1.6.3 事务四大特性

![image-20221013093611347](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013093611347.png)



#### 1.6.4 并发事务问题

![image-20221013094004001](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013094004001.png)

 ![image-20221013094233650](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013094233650.png)

这三个问题的讲解可以参考下https://www.bilibili.com/video/BV1Kr4y1i7ru/?p=54&spm_id_from=pageDriver&vd_source=b592fd0fd3bd041bab6398e89668385d

#### 1.6.5 事务隔离级别

![image-20221013094459967](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013094459967.png)

隔离级别的设置

![image-20221013094540836](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013094540836.png)

```sql
select @@TRANSACTION_ISOLATION;

set session transaction isolation level serializable;
```

https://www.bilibili.com/video/BV1Kr4y1i7ru/?p=55&spm_id_from=pageDriver&vd_source=b592fd0fd3bd041bab6398e89668385d

##  2. 进阶篇

###  2.1 存储引擎

####  2.1.1 MySQL体系结构 

![image-20221013100913948](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013100913948.png)





#### 2.1.2 存储引擎简介

![image-20221013101044099](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013101044099.png)

```sql
-- 查看存储引擎
show create table account;
```

- 在创建表时指定存储引擎

```sql
create table account(
	字段1 字段1类型 
) ENGINE = INNODB;
```



- 查看当前数据库所支持的存储引擎

```sql
show engines ;
```

![image-20221013101342823](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013101342823.png)



#### 2.1.3 存储引擎特点

- InnoDB

![image-20221013101733840](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013101733840.png)

参数innodb_file_per_table 表示使用innoDB的table是否公用一个xxx.idb文件

```sql
show variables  innodb_file_per_table;
```

可以通过命令行`ibd2sdi xxx.idb` 查看sdi信息

![image-20221013102001476](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013102001476.png)

![image-20221013102929782](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013102929782.png)

- MyISAM

![image-20221013103015710](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013103015710.png)

- Memory

![image-20221013103214030](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013103214030.png)



- 存储引擎的特点

![image-20221013103250265](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013103250265.png)

#### 2.1.4 存储引擎选择

- 存储引擎的选择

![image-20221013103514278](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013103514278.png)



###  2.2 索引

 

####  2.2.1 索引概述

![image-20221013105545152](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013105545152.png)

- 演示(无索引与有索引)

![image-20221013105731805](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013105731805.png)

无索引时就算匹配到了结果一会进行全表扫描

- 索引的优缺点

![image-20221013105937803](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013105937803.png)



#### 2.2.2 索引结构

mysql的索引是在存储引擎层实现的,不同的存储引擎有不同的结构,主要包含以下几种

![image-20221013110144844](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013110144844.png)



![image-20221013110211033](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013110211033.png)

注:平常所说的索引,如果没有特别指明,都是b+树索引.

#####  2.2.2.1 BTree

![image-20221013110536585](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013110536585.png)

##### 2.2.2.2 BTree(多路平衡查找树)

![image-20221013110716364](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013110716364.png)

数据结构可视化网站:
https://www.cs.usfca.edu/~galles/visualization/Algorithms.html

##### 2.2.2.3 B+Tree 

![image-20221013111423463](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013111423463.png)

mysql中的B+树

![image-20221013111549959](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013111549959.png)



##### 2.2.2.4 hash

![image-20221013111939582](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013111939582.png)

特点

![image-20221013112007366](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112007366.png)

![image-20221013112031885](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112031885.png)

##### 2.2.2.5 思考

![image-20221013112354201](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112354201.png)



#### 2.2.3 索引分类

![image-20221013112507292](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112507292.png)

 在innoDB存储引擎中,根据索引的存储形式,又可以分为一下两种:

![image-20221013112641053](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112641053.png)

聚集索引的选取规则:

![image-20221013112811812](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112811812.png)



![image-20221013112956114](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013112956114.png)



- 思考

  ![image-20221013145055302](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013145055302.png)

![image-20221013145457746](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013145457746.png)

#### 2.2.4 索引语法

![image-20221013145614681](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013145614681.png)



- 案例

![image-20221013145738639](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013145738639.png)

```sql
-- 数据准备

create table tb_user(
	id int primary key auto_increment comment '主键',
	name varchar(50) not null comment '用户名',
	phone varchar(11) not null comment '手机号',
	email varchar(100) comment '邮箱',
	profession varchar(11) comment '专业',
	age tinyint unsigned comment '年龄',
	gender char(1) comment '性别 , 1: 男, 2: 女',
	status char(1) comment '状态',
	createtime datetime comment '创建时间'
) comment '系统用户表';


INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('吕布', '17799990000', 'lvbu666@163.com', '软件工程', 23, '1', '6', '2001-02-02 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('曹操', '17799990001', 'caocao666@qq.com', '通讯工程', 33, '1', '0', '2001-03-05 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('赵云', '17799990002', '17799990@139.com', '英语', 34, '1', '2', '2002-03-02 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('孙悟空', '17799990003', '17799990@sina.com', '工程造价', 54, '1', '0', '2001-07-02 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('花木兰', '17799990004', '19980729@sina.com', '软件工程', 23, '2', '1', '2001-04-22 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('大乔', '17799990005', 'daqiao666@sina.com', '舞蹈', 22, '2', '0', '2001-02-07 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('露娜', '17799990006', 'luna_love@sina.com', '应用数学', 24, '2', '0', '2001-02-08 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('程咬金', '17799990007', 'chengyaojin@163.com', '化工', 38, '1', '5', '2001-05-23 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('项羽', '17799990008', 'xiaoyu666@qq.com', '金属材料', 43, '1', '0', '2001-09-18 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('白起', '17799990009', 'baiqi666@sina.com', '机械工程及其自动化', 27, '1', '2', '2001-08-16 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('韩信', '17799990010', 'hanxin520@163.com', '无机非金属材料工程', 27, '1', '0', '2001-06-12 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('荆轲', '17799990011', 'jingke123@163.com', '会计', 29, '1', '0', '2001-05-11 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('兰陵王', '17799990012', 'lanlinwang666@126.com', '工程造价', 44, '1', '1', '2001-04-09 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('狂铁', '17799990013', 'kuangtie@sina.com', '应用数学', 43, '1', '2', '2001-04-10 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('貂蝉', '17799990014', '84958948374@qq.com', '软件工程', 40, '2', '3', '2001-02-12 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('妲己', '17799990015', '2783238293@qq.com', '软件工程', 31, '2', '0', '2001-01-30 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('芈月', '17799990016', 'xiaomin2001@sina.com', '工业经济', 35, '2', '0', '2000-05-03 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('嬴政', '17799990017', '8839434342@qq.com', '化工', 38, '1', '1', '2001-08-08 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('狄仁杰', '17799990018', 'jujiamlm8166@163.com', '国际贸易', 30, '1', '0', '2007-03-12 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('安琪拉', '17799990019', 'jdodm1h@126.com', '城市规划', 51, '2', '0', '2001-08-15 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('典韦', '17799990020', 'ycaunanjian@163.com', '城市规划', 52, '1', '2', '2000-04-12 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('廉颇', '17799990021', 'lianpo321@126.com', '土木工程', 19, '1', '3', '2002-07-18 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('后羿', '17799990022', 'altycj2000@139.com', '城市园林', 20, '1', '0', '2002-03-10 00:00:00');
INSERT INTO itcast.tb_user (name, phone, email, profession, age, gender, status, createtime) VALUES ('姜子牙', '17799990023', '37483844@qq.com', '工程造价', 29, '1', '4', '2003-05-26 00:00:00');
```



```sql
-- 查看当前存在的索引
show index from tb_user;

-- 1.name字段为姓名字段,该字段的值可能会重复,为该字段创建索引
-- 新建索引 为tb_user表的name字段创建名为idx_user_name的索引
create index idx_user_name on tb_user (name);

-- 2.2phone手机号字段的值,非空,且唯一,为该字段创建唯一索引
create unique index idx_user_phone on tb_user (phone);
-- 3.为profession,age,status创建联合索引(在创建索引时,这些索引键的先后顺序需要注意的-->后面章节会详细讲述)

create index idx_user_pro_age_sta on tb_user (profession,age,status);


-- 4.为email建立合适的索引来提升查询效率
create index idx_user_email on tb_user(email);


-- 5.删除索引
drop index idx_user_email on tb_user;
```

![image-20221013152248196](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013152248196.png)



#### 2.2.5 SQL性能分析

- sql执行频率

```sql
show global status like 'Com_______'; -- Com后面七个下划线
```

![image-20221013153204977](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013153204977.png)



#####  2.2.5.1 慢查询日志

![image-20221013153348177](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013153348177.png)

```sql
show variables like 'slow_query_log';
```

![image-20221013153526525](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013153526525.png)

```properties
## 开启mysql蛮日志查询开关
show_query_log = 1;
## 设置慢日志的时间为2秒,sql语句执行时间超过2秒,就会是为慢查询,记录慢查询日志
long_query_time = 2;
```



![image-20221013160739169](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013160739169.png)



配置完毕后,通过以下质量重新启动mysql服务器进行测试,查看慢日志文件中记录的信息

`/var/lib/mysql/localhost-slow.log`

对于docker下的mysql推荐使用如下方法

```sql
set global slow_query_log='ON'; 

set global slow_query_log_file='/var/lib/mysql/data/slow.log';
--如果设置不了也可以直接查看保存位置
show variables like 'slow_query_log_file';

set global long_query_time=1;
```

##### 2.2.5.2 profile详情

show profiles能够在做sql优化时帮助我们了解时间都小号到哪里去了.通过have_profiling参数,能够看到当前mysql是否支持profile操作:

```sql
SELECT @@have_profiling;
```

默认profileing是关闭的,可以通过set语句在session/global级别开启profiling:

```sql
set profiling=1;
```



执行一系列的业务sql的操作,然后通过如下指令查看指令的执行耗时:

```sql
show profiles;
-- 通过show profiles 获取想要查看的id
show profile from query query_id;

show profile cpu for query query_id;
```



##### 2.2.5.3 explain执行计划

 ![image-20221013171553561](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013171553561.png)

![image-20221013172612192](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013172612192.png)

![image-20221013172653189](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013172653189.png)

#### 2.2.6 索引使用规则

- 验证索引效率

![image-20221013173044588](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013173044588.png)

#####  2.2.6.1 最左前缀法则

现在有如下索引

![image-20221013173459283](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013173459283.png)

![image-20221013173332270](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013173332270.png)

情况一查询profession,age,status索引有效

![image-20221013173605303](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013173605303.png)

情况二查询profession,age并没有跳过中间列,索引有效

![image-20221013173832513](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013173832513.png)

情况三查询profession,索引有效

![image-20221013173925867](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013173925867.png)

情况四查询age与status,索引失效,启用了全表扫描

![image-20221013174054703](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013174054703.png)



情况五查询status,索引失效

![image-20221013174131324](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013174131324.png)

情况六查询profession与status,索引有效,但是观察这里的key_len与情况三相同,说明status并未走索引,为单索引

![image-20221013174321939](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013174321939.png)

 

情况六,若调换三个参数的位置是否能走索引呢

![image-20221013190732016](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013190732016.png)

可以发现key_len为54说明三个字段都用上了,这表明最左原则要求字段存在,但不是要求必须在sql语句的最左.



##### 2.2.6.2 范围查询

联合索引中,出现范围查询(>,<),范围查询*右侧*的列索引失效.

![image-20221013191106895](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013191106895.png)

![image-20221013191126441](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013191126441.png)

![image-20221013191133730](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013191133730.png)

##### 2.2.6.3 索引失效

- 索引列运算

不要在索引列上进行运算操作,索引会失效.

```sql
explain select * from tb_user where substring(phone,10,2) = '15';
```

![image-20221013191916920](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013191916920.png)

![image-20221013191948281](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013191948281.png)

- 字符串不加引号

单索引时

![image-20221013192149747](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013192149747.png)

多索引时

![image-20221013192228727](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013192228727.png)

![image-20221013192239841](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013192239841.png)

- 模糊查询

如果仅仅是尾部模糊匹配,索引不会失效,如果是头部模糊匹配,索引失效.

- or连接的条件

用or分隔开的条件,如果or前的条件中的列有索引,而后面的列中没有索引,那么涉及到的索引不会被用到.

这里id有索引而age没有索引

![image-20221013193051398](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013193051398.png)

如果要使用索引的话可以给age也加入索引

- 数据分布影响

如果mysql评估使用索引比全表更慢,则不使用索引

 核心就是,如果通过索引过滤出来的数据是极少的数据就会走索引,否则全表扫描![image-20221013193606531](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013193606531.png)

![image-20221013193623278](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013193623278.png)

#####  2.2.6.4 sql提示

当某一字段同时存在联合索引和单列索引他会怎么选择呢?

![image-20221013194152983](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013194152983.png)

可以看到他选择是的联合索引,这是有innodb决定的.

那我们可以手动选择使用哪个索引吗?

- sql提示

sql提示,是优化数据库的一个重要手段,简单来说,就是在sql语句中加入一些认为的提示来达到优化操作的目的.

```sql
-- user index
explain select * from tb_user user index(inx_user_pro) where profession = '软件工程';

-- ignore index
explain select * from tb_user ignore index(inx_user_pro) where profession = '软件工程';

-- force index 强制使用
explain select * from tb_user force index(inx_user_pro) where profession = '软件工程';

```

#####  2.2.6.5 覆盖索引&回表查询

- 覆盖索引

尽量使用覆盖索引(查询使用了索引,并且需要返回的列,在该索引中已经全部能够找到),减少select 



![image-20221013195428613](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013195428613.png)

![image-20221013195453196](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013195453196.png)

![image-20221013195501596](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013195501596.png)



分析:

- 不需要回表的情况

![image-20221013195630575](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013195630575.png)

叶子节点有全部信息

- 覆盖索引的情况(这里只需要查询id与name,辅助索引里面全有,不需要回表)

![image-20221013195750191](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013195750191.png)

-    需要回表

包含了gender字段,此字段在辅助索引中不存在,因此需要查询聚集索引

![image-20221013195924725](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013195924725.png)

所以要避免使用select* 这样很容易出现回表查询.

- 思考

![image-20221013200244110](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013200244110.png)



解决方案是为username与password建立联合索引,这样性能比单独给user'name建立索引的性能好

#####  2.2.6.6 前缀索引

  当字段类型为字符串(varchar,text等)时,有时候需要索引很长的字符串,这会让索引变得很大,查询时,浪费大量的磁盘IO,影响查询效率.此时可以只将字符串的一部分前缀,建立索引,这样可以大大节约索引空间,从而提高索引效率.

```sql
-- 语法规则

create index idx_xxxx on table_name(column(n))

-- eg
create index inx_user_phone on tb_user(phone(6))


```

- 前缀长度

可以根据索引的选择性来决定,而选择性是指不重复的索引值(基数)和数据表的记录总数的比值,索引选择性越高则查询效率越高.唯一索引的选择性是1,这是最好的索引选择性,性能也是最好的.

公式:

```sql
select count(distinct email)/count(*) from tb_user;

select count(distinct substring(email,1,5))/count(*) from tb_user;
```

- 前缀索引查询流程

![image-20221013202006235](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013202006235.png)

若id=1如出来的数据不匹配则会取出lvbu6链表的下一个其对应的id,并取出id对应的email,若匹配则查询成功返回.

##### 2.2.6.7 单列&联合索引

![image-20221013202614417](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013202614417.png)

- 联合索引情况

根据创建的索引会先对phone进行排序phone相同再对name进行排序 ![image-20221013202702237](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013202702237.png)

#### 2.2.7 索引设计原则

 ![image-20221013204005921](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013204005921.png)



###  2.3  SQL优化

####  2.3.1 插入数据

- insert优化

![image-20221013205145732](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013205145732.png)

- 大批量插入数据

![image-20221013205221681](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221013205221681.png)



```shell
#客户端连接服务端时,加上参数 --local-infile
mysql --local-infile -u root -p
```

设置全局参数local_infile为1,开启从本地加载文件导入数据的开关

```sql
set global local_infile=1


-- 执行load命令将准备好的数据,加载到表结构中 该文件格式如上左图所示

load data local infile '/root/sql1.sql' in to table 'tb_user' fields terminated by ',' lines terminated by '\n';
```

####  2.3.2 主键优化

- 数据组织方式

再InnoDB存储引擎中,表数据都是根据主键顺序组织存放的,这种存储方式的表称为索引组织表(index organized table IOT) 

![image-20221014084150378](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014084150378.png)

- 页分裂

页可以为空,也剋填充一半,也可以填充100%.每个页包含了2-N行数据(如果一行数据过大,会溢出),根据主键排列.

主键顺序插入:

![image-20221014084507803](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014084507803.png)

主键乱序插入:

![image-20221014084620878](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014084620878.png)

![image-20221014084636744](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014084636744.png)

该插入page1但是page1已经满了,于是需要进行页分裂

于是找到page1一半的位置,将后半段移动到新的page中,并且将新page插入page1与page2之间

![image-20221014084923120](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014084923120.png)

![image-20221014084958025](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014084958025.png)

![image-20221014085121670](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014085121670.png)

- 页合并

当删除一行记录时,实际上记录并未被物理删除,只是记录被标记(flaged)为删除并且它的空间变得运行其他记录声明使用

当页中删除的记录达到了MERGE_THRESHOLD(默认为页的50%,可在创建表或者索引时指定),InnoDB会开始寻找最靠近的页(前或后)看看是否可以将合并以优化空间

![image-20221014085642766](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014085642766.png)

![image-20221014085658259](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014085658259.png)

- 主键设计原则

![image-20221014085905204](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014085905204.png)



#### 2.3.3 order by优化

1. Using filesort:通过表的索引或全表扫描,读取满足条件的数据行,然后在缓冲区sort buffer中完成排序操作,所有不是通过索引直接返回排序结果的排序都叫FileSort排序.
2. Using index:通过有序索引顺序扫描直接返回有序数据,这种情况即为using index,不需要额外排序,操作效率高.

- 没有建立索引时

`explain selectid,age,phone from tb_user order by age,phone`

![image-20221014091425228](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014091425228.png)

- 建立age与phone索引后

```sql
create index inx_user_age_phone on tb_user(age,phone);
```

![image-20221014091638658](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014091638658.png)

再次进行排序

```sql
explain select id,age,phone from tb_user order by age;

explain select id,age,phone from tb_user order by age,phone;
```



![image-20221014091703985](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014091703985.png)

![image-20221014091827181](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014091827181.png)

- age倒序,phone倒序

```sql
explain select id,age,phone from tb_user order by age desc,phone desc;
```

![image-20221014091925127](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014091925127.png)

此时依旧是user index,但是出现了Backward index scan ,这是因为创建索引时没有选择key的排序方式,因此默认为升序,所以phone降序则采用的反向扫描.

我们可以查看下建立的索引排序规则(A则代表升序)

![image-20221014093320535](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014093320535.png)

- 先对phone进行排序,再对age进行排序

```sql
explain select id,age,phone from tb_user order by phone,age;
```

![image-20221014092235538](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014092235538.png)

猜测出现using index的原因是因为他在排序时使用了index,但是这里的索引是以age先排再phone排,这与返回的不同,这里需要借助sort buffer来进行重新排序.另一种解释是说这里采用了覆盖索引,因为id,age,phone,都在idx_user_age_phone里面不用回表查询,但是order没办法使用索引.

- 按照age 升序,phone降序

```sql
explain select id,age,phone from tb_user order by age asc ,phone desc
```

![image-20221014093827747](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014093827747.png)

还是会出现sort buffer排序

如果要优化我们可以新建一个索引

```sql
create index inx_user_age_phone_ad on tb_user(age asc , phone desc);
```

![image-20221014094020272](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014094020272.png)

再次执行,发现优化成功

![image-20221014094240191](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014094240191.png)



- 小结

![image-20221014094711460](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014094711460.png)

可以通过以下命令查看缓冲区大小

```sql
show variables like 'sort_buffer_size';
```



#### 2.3.4 group by优化

当表中只有聚集索引时

![image-20221014094951239](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014094951239.png)

```sql
explain select profession ,count(*) from tb_user froup by profession;
```

![image-20221014095119695](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014095119695.png)



现在创建一个索引

```sql
explain index idx_user_pro_age_sta on tb_user (profession,age,status);
```

![image-20221014095326931](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014095326931.png)



若根据age分组

```sql
explain select age ,count(*) from tb_user group by age;
```

![image-20221014095524538](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014095524538.png)

这里使用了index是因为,select数据列只用从idx_user_pro_age_sta而不用去回表查看聚集索引.而出现user temporary是因为selectage不包括prodession,在select中加入profession则可以解决

```sql
explain select profession,age ,count(*) from tb_user group by age;
```

![image-20221014100447852](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014100447852.png)

现在我们依旧只select age但是我们给他加一个限制条件只选择profession='软件工程的'

```sql
explain select age ,count(*) from tb_user where profession = '软件工程' group by age;
```

![image-20221014100712377](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014100712377.png)

发现也满足最左前缀法则

#### 2.3.5 limit优化

一个常见又非常头疼的问题是limit 2000000,10,此时需要mysql排序前2000010条记录,仅仅返回最后10条

,其他记录丢弃,查询代价较大.

优化思路:一般查询分页时,通过创建 覆盖所有能够比较好的提高性能,可以通过覆盖索引加子查询的方式进行优化.

```sql
explain select t.* from tb_sku t,(select id from tb_sku order by id limit 2000000,10) a where t.id = a.id;
```

- 不加order

```sql
-- 较小时耗时短
explain select * from tb_sku limit 10,10;
--  较大时耗时猛增
explain select * from tb_sku limit 1000000,10;
```

- 加入order字段

```sql
-- 与上一条语句相比,时间明显下降
explain select * from tb_sku  order by id limit 1000000,10;
```

- 子查询

```
explain select t.* from tb_sku t,(select id from tb_sku order by id limit 2000000,10) a where t.id = a.id;
```

#### 2.3.6 count优化

```sql
explain select count(*) from tb_user
```

- MyISAM 引擎把一个表的总行数存在磁盘上,因此执行count(*)的时候会直接返回这个数,效率高
- InnoDB引擎较为蛮烦,他只想count(*)时候,需要把数据一行一行读出来,然后累计计数

优化思路:自己计数(redis等)

---

- count用法

![image-20221014104036049](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014104036049.png)

![image-20221014103923224](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014103923224.png)

count字段时,会判断字段是否为null,若为null 则不会计数+1

![image-20221014104207985](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014104207985.png)

![image-20221014104226359](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014104226359.png)

![image-20221014104244757](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014104244757.png)

#### 2.3.7  update优化

https://www.bilibili.com/video/BV1Kr4y1i7ru/?p=95&spm_id_from=pageDriver&vd_source=b592fd0fd3bd041bab6398e89668385d

行锁与表锁

- 行锁情况

现有两个线程(都开启事务),线程1更新id=1的数据,在线程1commit之前线程2更新id=4的数据.(id是有聚集索引的)

```sql
-- 线程1
begin; 
update tb_user set name = 'newName' where id = 1;
--在线程1提交之前
-- 线程2 
begin;
update tb_user set name = 'newNameT2' where id = 4; --此时为行锁 本次提交不会阻塞

-- 线程1
commit;
-- 线程2
commit;

```

- 表锁情况

现有两个线程(都开启事务),线程1更新name='张三'的数据,在线程1commit之前线程2更新name='李四'的数据.(现在name没有建立索引,会产生表锁)

```sql
-- 线程1
begin; 
update tb_user set name = 'newName' where name = '张三';
--在线程1提交之前
-- 线程2 
begin;
update tb_user set name = 'newNameT2' name = '李四'; --此时为表锁 本次提交会阻塞

-- 线程1
commit; -- 知道线程1commit 线程2 的update命令才会执行
-- 线程2
commit;
```

- 解决表锁

现在给name加入索引,此时就不会出现表锁

```sql
-- 线程1
begin; 
update tb_user set name = 'newName' where name = '张三';
--在线程1提交之前
-- 线程2 
begin;
update tb_user set name = 'newNameT2' name = '李四'; --此时为行锁 本次提交不会阻塞

-- 线程1
commit;
-- 线程2
commit;
```

![image-20221014105601885](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014105601885.png)

### 2.4 视图

####  2.4.1 介绍

![image-20221014110109059](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014110109059.png)

- 创建

![image-20221014110309154](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014110309154.png)

```sql
create or replace view tb_user_v1 as select id,name from tb_user where id<=10; 
```

- 查询

![image-20221014110716089](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014110716089.png)



- 修改

![image-20221014110742569](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014110742569.png)

```sql
create or replace view tb_user_v1 as select id,name,phone from tb_user where id<=5;

alter view tb_user_v1 as select id,name,phone from tb_user where id<=5;
```

- 删除

![image-20221014110758000](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014110758000.png)

```sql
drop view if exist tb_user_v1
```

#### 2.4.2 检查选项(cascaded)

现在向tb_user_v1插入一条数据id=5的数据

```sql
inset into tb_user_v1 values(5,'woldier');


inset into tb_user_v1 values(10,'woldier10');
```

发现插入成功,tb_user_v1与tb_user里面都可以查看到

如果id为10大于5呢?

发现插入成功但是,tb_user_v1中找不到这条数据,这是因为tb_user_v1的建立语句中有where id<= 5;

为了避免插入到了view中但是却在view中不出现,我们可以在建立视图时加入限定

```sql
create or replace tb_user_v1 as as select id,name,phone from tb_user where id<=5 with cascaded check option;
```

- cascaded限定

![image-20221014111743698](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014111743698.png)

若设为cascaded不仅会检查当前的限定条件还会检查所依赖视图的限定条件.

- local限定

![image-20221014112325520](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014112325520.png)

local下会递归检查有限定语句的,有限定语句会判定是否满足条件,若没加判定选项则不会检查.

#### 2.4.3 更新及作用

![image-20221014143415417](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014143415417.png)

要使view中的行可以更新,必须让view和表中数据一一对应.



- 作用

![image-20221014143618973](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014143618973.png)

###  2.5 存储过程

#### 2.5.1 介绍

![image-20221014144238388](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014144238388.png)



#### 2.5.2 基本语法

- 创建

![image-20221014144508373](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014144508373.png)

```sql
create procedure p1()
begin
	select count(*) from student;
end;
```



- 调用

![image-20221014144531861](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014144531861.png)

```sql
call p1();
```

- 查看

![image-20221014145210518](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014145210518.png)



```sql
-- 查询指定数据库下的存储过程
select * from INFORMATION_SCHEMA.ROUTINES WHERE ROUTINE_SCHEMA = 'woldierDB' 
-- 查询某个存储过程的定义
show create procedure p1();
```

![image-20221014145625347](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014145625347.png)

![image-20221014145721886](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014145721886.png)

- 删除

```sql
drop procedure if exists p1;
```

注意:

![image-20221014150321199](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014150321199.png)

在命令行新建的时候他会认为sql语句的分号为结束符,因此存储过程新增失败

可以通过命令

```sql
delimiter $$ --指定结束符为$$
```

之后将原有语句稍作修改即可

```sql
create procedure p1()
begin
	select count(*) from student;
end$$
```

#### 2.5.3 变量

#####  2.5.3.1 系统变量

show后面没指定session还是global的话默认为session

![image-20221014150914175](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014150914175.png)

```sql
select @@session.autocommit;
select @@global.autocommit;

set session autocommit = 0;

```





##### 2.5.3.2 用户自定义变量

![image-20221014151551590](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014151551590.png)

```sql
-- 插入
set @name = 'woldier';
set @age := 18;
select @gender:= '男',@hobby:='java';
select age into @u_age from tb_user where name = '嬴政';

-- 查看
select @name;
select @age;
SELECT @gender,@hobby;

-- 使用变量
SELECT * from tb_user WHERE id =@age;


```





##### 2.5.3.3 局部变量

![image-20221014152442351](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014152442351.png)

![image-20221014152459464](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014152459464.png)

```sql
create procedure p2()
begin
	declare temp_x int default 0;
	select count(*) into  temp_x from tb_user;
	select temp_x;
end;


-- 调用
call p2;
```

#### 2.5.4 if判断

![image-20221014153645024](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014153645024.png)



- 练习

![image-20221014153715394](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014153715394.png)

```sql
create procedure p3()
begin 
	declare score int default 58;
	declare result varchar(10);
	if score >= 85 then 
		set result = '优秀';
	elseif score >= 60 then 
		set result = '及格';
	else 
		set result = '不及格'; 
	end if;
	select result;
end;
```

#### 2.5.5 参数

![image-20221014155249425](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014155249425.png)

 ```sql
create procedure p4(in score int,out result varchar(10))
begin 
	if score >= 85 then 
		set result = '优秀';
	elseif score >= 60 then 
		set result = '及格';
	else 
		set result = '不及格'; 
	end if;
end;

-- 
call p4(68,@res);
select @res;


-- 将传入的200分制的分数换算成百分制,然后返回

create procedure p5(inout score double)
begin
	set score = score * 0.5;
end;

-- 
set @score = 75;
call p5(@score);
select @score;
 ```

#### 2.5.6 case

![image-20221014160305861](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014160305861.png)

![image-20221014160351759](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014160351759.png)

```sql
create procedure p6(in m int ,out res varchar(10))
begin
	case
		when m>=1 and m<4 then 
			set res = '第一季度';
		when m>=4 and m<7 then 
			set res = '第二季度';
		when m>=7 and m<10 then 
			set res = '第三季度';
		when m>=10 and m<13 then 
			set res = '第四季度';
		esle 
			set res = '非法参数';
		end case;
end;

call p6(11,@res);
select @res;
```



#### 2.5.7  循环

- while

![image-20221014161952926](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014161952926.png)

```sql
-- 计算从1累加到n的值
create procedure p7(in n int,out res int)
begin 
	declare i int default 1;
	declare sum int default 0;
	while  i < n do
		set sum = sum + i;
		set i = i + 1 ;
	end while;
	set res = sum;
end;

-- 
call p7(50,@res);

select @res;
```

- repeat

![image-20221014162721138](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014162721138.png)

```sql
-- 计算从1累加到n的值
create procedure p8(in n int,out res int)
begin 
	declare i int default 1;
	declare sum int default 0;
	repeat 
		set sum =sum + i;
		set i = i+1;
		until n=i
	end repeat;
	set res = sum;
end;

-- 
call p8(50,@res);

select @res;

```

- loop

![image-20221014163154381](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014163154381.png)

![image-20221014163216660](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014163216660.png)

![image-20221014163230920](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014163230920.png)

![image-20221014163540787](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014163540787.png)

累加0-n的偶数

![image-20221014163706862](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014163706862.png)

#### 2.5.8 游标cursor

![image-20221014191310147](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014191310147.png)

返回表会报错

![image-20221014191340770](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014191340770.png)

![image-20221014191359153](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014191359153.png)

- 获取游标记录

```sql
FETCH 游标名称 INTO 变量 [,变量]
```

![image-20221014191416603](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014191416603.png)



- 案例

![image-20221014191442702](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014191442702.png)

```sql
create procedure p11(in age int)
begin

	declare uname varchar(100);
	declare upro varchar(100);
	-- 游标声明必须在 变量声明之后
	declare u_cursor cursor for select name,profession from tb_user  where age <= age;
	
	
	
	
	drop table if exists tb_user_pro;
	create table in not exists tb_user_pro(
    	id int primary key auto_increment,
        name varchar(100),
        profession varchar(100)
    );
    
    -- 开启游标
    open u_cursor;
    
    while true do
    	fetch u_cursor into uanme,upro;
    	insert into tb_user_pro values (null,uname,upro);
    end while;
    
    -- 关闭游标
    close u_cursor;

end;
```



上面这个procedure会新建一张table,并且也会将数据插入这张表,但是会出现报错:

no row to fetch

这是因为while没有结束循环.





#### 2.5.9 条件处理程序

  条件处理程序(Handler)可以用来定义在流程控制结构执行过程中遇到问题时相应的处理步骤.具体语法为:

![image-20221014193327242](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014193327242.png)

```sql
create procedure p11(in age int)
begin

	declare uname varchar(100);
	declare upro varchar(100);
	-- 游标声明必须在 变量声明之后
	declare u_cursor cursor for select name,profession from tb_user  where age <= age;
	-- 
	declare exit handler for SQLSTATE '02000' close u_cursor
	-- 具体的错误代码也可用替代代码简写
	declare exit handler for NOT FOUND close u_cursor
	
	
	
	drop table if exists tb_user_pro;
	create table in not exists tb_user_pro(
    	id int primary key auto_increment,
        name varchar(100),
        profession varchar(100)
    );
    
    -- 开启游标
    open u_cursor;
    
    while true do
    	fetch u_cursor into uanme,upro;
    	insert into tb_user_pro values (null,uname,upro);
    end while;
    
    -- 关闭游标
    close u_cursor;

end;
```



### 2.6 存储函数

![image-20221014194039349](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014194039349.png)

```sql
-- 存储函数

-- 从1累加到n
create function fun1(n int)
returns int
begin

	declare total int default 0;
	
	while n>=0 do
		set total = total + n;
		set n = n - 1;
	end while;


	return total;
end;

```

![image-20221014194552270](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014194552270.png)

以上产生错误,提示我们必须要指定charecteristic

```sql
-- 存储函数

-- 从1累加到n
create function fun1(n int)
returns int deterministic
begin

	declare total int default 0;
	
	while n>=0 do
		set total = total + n;
		set n = n - 1;
	end while;


	return total;
end;

--
select fun1(100) 

```

###  2.7 触发器

- 介绍

![image-20221014195219419](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014195219419.png)

- 语法

![image-20221014195357586](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014195357586.png)

练习:

![image-20221014195932383](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014195932383.png)

```sql
-- 准备工作
create table user_logs(
  id int(11) not null auto_increment,
  operation varchar(20) not null comment '操作类型, insert/update/delete',
  operate_time datetime not null comment '操作时间',
  operate_id int(11) not null comment '操作的ID',
  operate_params varchar(500) comment '操作参数',
  primary key(`id`)
)engine=innodb default charset=utf8;


-- 插入触发器
create trigger tb_user_insert_trigger
after insert 
on tb_user for each row 
begin 
	insert into user_logs (id,operation,operate_time,operate_id,operate_params) 
		values (null,'insert',now(),new.id,concat('inset :','name=',new.name,',phone=',new.phone,',profession=',new.profession,',email=',new.email));
end; 


-- 查看触发器
show TRIGGERS;

-- 删除
drop trigger tb_user_insert_trigger

-- 插入数据到tb_user观察user_logs是否发生变化


insert into tb_user(id, name, phone, email, profession, age, gender, status, createtime)
VALUES (25,'二皇子','18809091212','erhuangzi@163.com','软件工程',23,'1','1',now());



```

![image-20221014201621263](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014201621263.png)

```sql
-- 插入update触发器

create trigger tb_user_update_trigger
after update 
on tb_user for each row 
begin 
	insert into user_logs (id,operation,operate_time,operate_id,operate_params) 
		values (null,'update',now(),new.id,concat('update:','name=',new.name,',phone=',new.phone,',profession=',new.profession,',email=',new.email,',name=',old.name,',phone=',old.phone,',profession=',old.profession,',email=',old.email
							
		));
end; 

-- 
update tb_user set age = 32 where id = 23;
```

![image-20221014202202734](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014202202734.png)

```sql
create trigger tb_user_delete_trigger
after delete 
on tb_user for each row 
begin 
	insert into user_logs (id,operation,operate_time,operate_id,operate_params) 
		values (null,'insert',now(),old.id,concat('inset :','name=',old.name,',phone=',old.phone,',profession=',old.profession,',email=',old.email));
end; 

delete from tb_user where id = 25;
```

![image-20221014202550031](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014202550031.png)

### 2.8 锁

![image-20221014204931816](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014204931816.png)



![image-20221014205020661](https://woldier-pic-repo-1309997478.cos.ap-chengdu.myqcloud.com/image-20221014205020661.png)
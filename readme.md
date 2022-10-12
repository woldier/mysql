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


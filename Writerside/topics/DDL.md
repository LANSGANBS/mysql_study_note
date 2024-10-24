# DDL

DDL (Data Definition Language) - 数据定义语言：用于定义和管理数据库结构的语言，包括创建、修改和删除数据库对象（如表、视图、索引等）。

1. DDL-数据库操作
```SQL
show tables; -- 查看所有表
create database mysql_study; -- 创建mysql_study数据库
use mysql_study; -- 使用mysql_study数据库
select database; -- 查看当前使用的数据库
drop database mysql_study; -- 删除mysql-study数据库
```
2. DDL-表操作
```SQL
show tables; -- 查看所有表
create table tb_use(
    id int comment '编号',
    name varchar(50) comment '姓名',
    age int comment '年龄',
    gender varchar(1) comment '性别'
)comment '用户表'; --创建tb_use表
desc tb_use; -- 查看tb_use表信息
show create table tb_use; -- 查看tb_use创建语句
alter table tb_use add nickName varchar(20); -- 在tb_use表中添加nickName
alter table tb_use change nickName userName varchar(20); -- 在tb_use表中 把nickName改变为userName
alter table tb_use drop userName; -- 在tb_use表中删除userName
alter table tb_use rename to table_use; -- 把tb_use重命名为table_use
drop table if exists table_use; --如果存在table_use表 则删除
```
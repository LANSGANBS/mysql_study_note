# DCL

DCL (Data Control Language) - 数据控制语言：用于控制对数据库的访问权限和安全性，包括授权和撤销权限的语句，如 GRANT 和 REVOKE。

- DCL-用户管理

1. 查询用户
```sql
   use mysql;
   select * from user; 
```
2. 创建用户
```sql
    create user '用户名'@'主机名' identified by '密码';
```
3. 修改用户密码
```sql
   alter user '用户名'@'主机名' identified with mysql_native_password by '新密码';
```
4. 删除用户
```sql
   drop user '用户名'@'主机名';
```

eg:
1. 创建用户itcast，只能够在当前主机Localhost访问，密码123456；
```sql
   create user 'itcast'@'Localhost' identified by '123456';
```
2. 创建用户heima，可以在任意主机访问该数据库，密码123456；
```sql
   create user 'heima'@'%' identified by '123456';
```
3. 修改用户heima的访问密码为1234；
```sql
   alter user 'heima'@'%' indentified with myqsl_native_password by '1234'; 
```
4. 删除itcast@LocaLhost用户
```sql
   drop user 'itcast'@'Localhost';
```

- DCL-权限控制

mysql提供的部分权限如下表所示：

| 权限                | 说明         |
|--------------------|------------|
| all,all privileges | 所有权限       |
| select             | 查询数据       |
| insert             | 插入数据       |
| update             | 修改数据       |
| delete             | 删除数据       |
| alter              | 修改表        |
| drop               | 删除数据库/表/视图 |
|create              | 创建数据库/表    |

1. 查询权限
```sql
   show grants for '用户名'@'主机名'；
   show grants for 'LANSGANBS'@'localhost'; -- 查询LANSGANBS的权限
```
2. 授予权限
```sql
   grant 权限列表 on 数据库名.表名 to '用户名'@'主机名';
   grant all on test.* to 'LANSGANBS'@'localhost'; -- 授予LANSGANBS对于test数据库的所有表的所有权限
```
3. 撤销权限
```sql
   revoke 权限列表 on 数据库名.表名 from '用户名'@'主机名';
   revoke all on test.* from 'LANSGANBS'@'localhost';
```
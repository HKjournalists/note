Mysql 用户权限相关


####查看用户权限

```
show grants for 'username'@'host'
```

####现有用户以及host信息，host(代表可以访问的IP)

```
SELECT DISTINCT CONCAT('User: ''',user,'''@''',host,''';') AS query FROM mysql.user;
```

####创建用户

```
CREATE USER 'username'@'host' IDENTIFIED BY 'password'; 
eg : 
	CREATE USER 'wangjia'@'%' IDENTIFIED BY '111111'
```
####赋予权限

```
grant 权限 on 数据库对象 to 用户
eg : 
	grant select, insert, update, delete on testdb.* to 'wangjia'@'%'
```
####创建的同时授予权限
```
 GRANT ALL ON *.* TO admin@'%' IDENTIFIED BY 'admin' WITH GRANT OPTION; 
```
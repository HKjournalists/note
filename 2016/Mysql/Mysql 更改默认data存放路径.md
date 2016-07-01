##Mysql 更改默认data存放路径

1.停止mysql服务

	service mysqld stop
	
2.修改ysql 配置文件 my.cnf （linux下默认路径：/etc/my.conf）
更改下面参数，/data/mysql 是更改后的路径

```
【mysqld】
datadir=/data/mysql
socket=/data/mysql/mysql.sock
[mysql]
socket=/data/mysql/mysql.sock
```

3.把原来data存放文件中得内容移动到新路径

```
mv /var/lib/mysql/* /data/mysql
```

4.修改启动文件参数

```
get_mysql_option mysqld datadir “/data/mysql”
```

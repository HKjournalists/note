##Memcached 

###1.下载  
  
###2.上传到服务器　　
scp  -i 位置 user@host:目录位置
####eg:
> **scp -i /Users/wangjia/java/tools/online/apptest.pem  /Users/wangjia/Downloads/memcached-1.4.25.tar.gz ec2-user@ec2-52-76-205-245.ap-southeast-1.compute.amazonaws.com:/tmp**
  
（也可以直接在服务器下载好。。）
###3.安装命令
> **sudo ./configure &&sudo make  && sudo make install**

###4.基本命令
启动选项：  
> -d是启动一个守护进程；  
> -m是分配给Memcache使用的内存数量，单位是MB；  
> -u是运行Memcache的用户；  
> -l是监听的服务器IP地址，可以有多个地址；  
> -p是设置Memcache监听的端口，，最好是1024以上的端口；  
> -c是最大运行的并发连接数，默认是1024；  
> -P是设置保存Memcache的pid文件。

基本命令：  
> **启动：memcached -p 11211 -m 64m -d**  
> **连接：telnet host port**  
> **set:　set　key　flags　 exptime　 bytes**  
> **　　　value**　　  
> －－参数说明如下：  
> －－－－key：键值 key-value 结构中的 key，用于查找缓存值。  
> －－－－flags：可以包括键值对的整型参数，客户机使用它存储关于键值对的额外信息 。  
> －－－－exptime：在缓存中保存键值对的时间长度（以秒为单位，0 表示永远）  
> －－－－bytes：在缓存中存储的字节数  
> －－－－noreply（可选）： 该数告知服务器不需要返回数据  
> －－－－value：存储的值（始终位于第二行）（可直接理解为key-value结构中的value）  
> **get: get key**
 

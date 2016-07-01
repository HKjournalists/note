##Linux cmd
###ps  进程
ps aux | grep name

###端口查看
 netstat -apn | grep 8080

###压缩
zip -r [dir...]
unzip [dir]

###tar
**解压**

```
tar -zxvf 待解压文件 -C 目的路径
tar xzvf expect5.45.tar.gz
```
**批量解压**

```
for tar in *.tar.gz
do tar -zxvf ${tar} -C /data/ttlog/sql/
done
```
**ps**
ps -ef 
ps -aux
 
**grep**
grep "str1\|str2"  包含str1或str2
grep -w "str1"     匹配整个单词



 
 
 
 

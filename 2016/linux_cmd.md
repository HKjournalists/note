##Linux cmd
###ps  进程
ps aux | grep name


###端口查看
 netstat -apn | grep 8080

###tar 
 范例一：将整个 /etc 目录下的文件全部打包成为 /tmp/etc.tar 
[root@linux ~]# tar -cvf /tmp/etc.tar /etc<==仅打包，不压缩！ 
[root@linux ~]# tar -zcvf /tmp/etc.tar.gz /etc<==打包后，以 gzip 压缩
[root@linux ~]# tar -jcvf /tmp/etc.tar.bz2 /etc<==打包后，以 bzip2 压缩 
     特别注意，在参数 f 之后的文件档名是自己取的，我们习惯上都用 .tar 来作为辨识。 
 如果加 z 参数，则以 .tar.gz 或 .tgz 来代表 gzip 压缩过的 tar file ～ 
 如果加 j 参数，则以 .tar.bz2 来作为附档名啊～ 
 上述指令在执行的时候，会显示一个警告讯息： 
 『tar: Removing leading `/" from member names』那是关於绝对路径的特殊设定。
#linux expect 初体验
###一、来由  
最近初试编写各种Linux shell script 来帮助提高工作效率，但是作为自动化的脚本，很头疼的是很多情况下都需要人为参与，比如输入password，输入确认信息yes/no。如何让这些交互命令自动完成？那就是expect了。
###二、expect是什么  
> Expect是一个免费的编程工具语言，用来实现自动和交互式任务进行通信，而无需人的干预  
>
> Chat脚本由一系列expect-send对组成：expect等待输出中输出特定的字符，通常是一个提示符，然后发送特定的响应.

一个简单的登录例子：实现自动登录

```
#!/usr/bin/expect
set timeout 30  #超时时间

spawn  ssh username@host   #给ssh运行进程加个壳，用来传递交互指令
expect "password:"         #expect
send "pwpwpwp\r"		   #模拟用户输入密码，\r表示enter
interact				   #交互权还给终端
```

###

* [expect用法](http://www.cnblogs.com/iloveyoucc/archive/2012/05/11/2496433.html)
* [使用expect实现shell自动交互](http://www.nginx.cn/1934.html)
* [shell中嵌套执行expect命令实例](http://www.jb51.net/article/58777.htm)
* [linux expect的使用详解](http://www.2cto.com/os/201305/209909.html)
* [linux expect简介及安装](http://blog.csdn.net/a19881029/article/details/8140874)
* [SHELL : expect安装](http://blog.csdn.net/teddy99999/article/details/19171045)





##MySql  
####查看执行日志.
> * http://blog.csdn.net/lissdy/article/details/40793187  
 
####timestamp
> *当插入和更新时，指定的timestamp值为null时，mysql中不予许timestamp为null,但是也不会报语法错误，而是将null值用当前时间替换。

####时间比较

>昨天  
>
    WHERE  TO_DAYS(NOW()) - TO_DAYS(create_date) =1
 
>昨天和今天  
>
    WHERE  TO_DAYS(NOW()) - TO_DAYS(create_date) =1
    
####mysql show processlist命令 详解
> * http://www.51testing.com/html/96/110296-69546.html 
    
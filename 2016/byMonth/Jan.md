## 1-29 ##
> **异步队列方式一般用来处理什么问题?**  
> **新起*spring context*做这种定时任务,一直执行的话,对性能有什么影响?**  
> **java下 memcached 的使用? 以及memcached了解**  
  
##
**---待实验(尼玛这下面就是基础扎不扎实带来的各种小问题啊)**
####数据库存null,那么查这个string(null) ,int(null)等字段时,那么resultSet.getString()和getInt()拿到的会是什么(null?0?""?)**设计数据库时,对这样的细节问题如何处理?
> **1.初步了解到当是Int等数值类型时查出来是NULL的时候,resultset.get的时候会自动将其替换成0(那数据库中NULL和0两种情况如何分辨?)  
2.ResultSet中的wasNull()...**  

##
####数据库设计时,一些可为NULL的字段,选择 default null,还是设置一个默认非空值?
> **特地在知乎问了几个数据库设计的小问题,包括这个,嗯,没有明确的答案,还是看情景再分析.....链接:https://www.zhihu.com/question/39967106/noti-answers?group_id=676714131255988224**
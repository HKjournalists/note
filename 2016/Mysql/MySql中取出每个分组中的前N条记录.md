
##MySql中取出每个分组中的前N条记录

公司开始做审计。。需要拉各种数据。  
于是有了下面的需求：

    2015年所有RMB玩家的最后一条充值记录，
    现在有个只有充值玩家的uid列表

> [ysql分组取每组前几条记录(排名) 附group by与order by的研究](mysql分组取每组前几条记录(排名) 附group by与order by的研究)
> 
> 



```
	CREATE VIEW rmb_player AS
	  SELECT *
	  FROM log_remove_i_money
	  WHERE `_time` < '2016-01-01 00:00:00' AND _account IN (      );
	
	CREATE VIEW ac_max_time AS
	  SELECT
	    _account,
	    max(`_time`) AS _time
	  FROM money_player
	  GROUP BY _account;
	
	#此时已经取出RMB玩家2015年最后一时间的消费记录
	CREATE VIEW last_data AS (
	  SELECT a.*
	  FROM money_player a, ac_max_time b
	  WHERE a._account = b._account AND a._time = b._time
	  ORDER BY a._account);
	
	##一个玩家可能一个时间有多笔消费，比如一次购买多个商品，此时需要留下玩家钱最少的那条。。
	SELECT a.*
	FROM last_data a, (SELECT
	                     `_account`,
	                     min(`_newrmb`) AS `_newrmb`
	                   FROM last_data
	                   GROUP BY `_account`) b
	WHERE a.`_account` = b.`_account` AND a.`_newrmb` = b.`_newrmb`;
```

整个思路还是很明确的。。不过这种事情还是写个代码来做比较好。。。



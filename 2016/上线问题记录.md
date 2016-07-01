##上线问题记录
###一、tomcat启动报错

    ERROR: transport error 202: bind failed: 地址已在使用
    ERROR: JDWP Transport dt_socket failed to initialize, TRANSPORT_INIT(510)
    JDWP exit error AGENT_ERROR_TRANSPORT_INIT(197): No transports initialized [debugInit.c:750]
    FATAL ERROR in native method: JDWP No transports initialized, jvmtiError=AGENT_ERROR_TRANSPORT_INIT(197)
    
原因tomcat Debug端口已被占用。。  
> 1、修改catalina.sh下配置   改端口。
> 2、禁用debug模式

###二、查看端口信息  
netstat -anp | grep portid

ps aux | grep *
##Maven 探索。。
用了maven也一段时间了，也仅仅是停留在基本会使用的程度。很多东西慢慢觉得还是值得细究的，遂有此文。

####一、资源文件的配置 
多个资源文件？

    <build>
        <finalName>11</finalName>
        <resources>
            <resource>
                <directory>src/main/resources</directory>
            </resource>
            <resource>
                <directory>src/main/resources.online</directory>
            </resource>
        </resources>
    </build>`
上面的路径中配置了两个资源文件目录，打包发现maven会把两个目录下的资源文件打包到项目中。  
那么问题来了：  
> **1、两个资源目录中有相同名字的文件，会怎么处理？**  
> - - - - > 百度的时候有人说后配置的会覆盖前面的配置的。**但是并不是这样！！！**实际中打包进  项目的是**第一个配置的！！**后面有相同资源文件并没有什么卵用。  
> - - - - >**所有目录下唯一的资源文件都会被打包进项目**
>   
> 2、当资源目录不配置时？  
> - - - - >会默认用resources下的资源的文件，其他的目录不会

####二、maven直接部署到本地tomcat
项目pom文件中插件：

       <plugins>
            <plugin>
                <groupId>org.apache.tomcat.maven</groupId>
                <artifactId>tomcat7-maven-plugin</artifactId>
                <version>2.2</version>
                <configuration>
                    <url>http://localhost:8080/manager/text</url>
                    <server>local-server</server>
                    <path>/maven-test</path><!--填build final name,即war包名-->
                </configuration>
            </plugin>
        </plugins>
        
tomcat用户权限添加（conf/tomcat-users.xml）： 

    <role rolename="manager-script"/>
    <role rolename="manager-gui"/>
    <user username="wangjia" password="wangjia" roles="manager-gui,manager-script"/>
maven添加server（conf/setting.xml)
 
    <server>
		<id>local-server</id>
		<username>wangjia</username>
		<password>wangjia</password>
	</server>
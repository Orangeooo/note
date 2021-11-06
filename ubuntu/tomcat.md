## tomcat

下载tomcat

```
wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.12/bin/apache-tomcat-10.0.12.tar.gz

tar -zxvf apache-tomcat-10.0.12.tar.gz

sudo chmod 755 -R apache-tomcat-10.0.12
```

修改启动脚本，tomcat下的bin内

```
sudo vim startup.sh
```

加入这些

```
#set java environment
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
export CLASSPATH=.:%{JAVA_HOME}/lib:%{JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH

#tomcat
此处填tomcat路径
export TOMCAT_HOME=/home/ubuntu/apache-tomcat-10.0.12
```

执行

```
sudo ./startup.sh
```

如果启动tomcat是jre路径不对

```
报错
Using CATALINA_BASE:   /home/ubuntu/apache-tomcat-10.0.12
Using CATALINA_HOME:   /home/ubuntu/apache-tomcat-10.0.12
Using CATALINA_TMPDIR: /home/ubuntu/apache-tomcat-10.0.12/temp
Using JRE_HOME:        /usr
```

先检查全局JRE_HOME

```
echo $JRE_HOME
```

如果没问题，有可能是Tomcat启动时使用了局部的JRE_HOME字段，此时可以通过强制规定Tomcat启动配置来解决

```
vim /bin/setclasspath.sh
```

添加

```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
```

关闭tomcat

```
./shutdown.sh 
```

修改tomcat监听端口

进入tomcat的conf文件下的server.xml更改端口号

<Connector port=

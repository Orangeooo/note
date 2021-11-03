## open jdk

```
sudo apt install openjdk-8-jre-headless

sudo apt install openjdk-8-jdk-headless
检查
java -version
```

环境变量

```
vim /etc/profile
```

```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
export PATH=${JAVA_HOME}/bin:$PATH
```

```bash
source /etc/profile
```

验证

```
echo $JAVA_HOME
```

## oracle jdk

```
wget https://download.oracle.com/otn/java/jdk/8u311-b11/4d5417147a92418ea8b615e228bb6935/jdk-8u311-linux-x64.tar.gz
```

发送文件给服务器

```
scp C:\Users\11613\Downloads\jdk-8u311-linux-x64.tar.gz ubuntu@cyhhhh.top:/home/ubuntu

tar -zxvf jdk-8u311-linux-x64.tar.gz
```

## 多版本jdk共存

```
sudo update-alternatives --install /old/java-8-openjdk-amd64/bin/java java /new/jdk1.8.0_211/bin/java 100

sudo update-alternatives --config java

```



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

修改apache监听端口

```
sudo vim /etc/apache2/ports.conf

sudo vim /etc/apache2/sites-enabled/000-default.conf

service apache2 stop

service apache2 start
```

修改tomcat监听端口

进入tomcat的conf文件下的server.xml更改端口号


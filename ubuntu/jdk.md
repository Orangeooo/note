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


zsh
~/.zshrc
```

```
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre
export PATH=${JAVA_HOME}/bin:$PATH
```

```bash
source /etc/profile

zsh
source ~/.zshrc
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
sudo update-alternatives --install /old/java-8-openjdk-amd64/bin/java java /new/jdk1.8.0_311/bin/java 100

切换版本
sudo update-alternatives --config java

```
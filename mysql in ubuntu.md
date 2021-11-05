# 远程Mysql完整步骤！！

## 安装

```bash
安装
sudo apt install mysql-server
初始化
sudo mysql_secure_installation
```

## 登录

```bash
mysql -u root -p
```

如果mysql root 账户的 plugin 是 auto_socket ，使用sudo

查看plugin：

```mysql
select user,host,plugin from mysql.user;
```

为了安全，新建一个mysql用户

```mysql
create user USERNAME@'%' identified by 'PSAAWORD';
create user user@'%' identified by '123456';
删除用户
DROP USER 'USERNAME'@'%';
```

修改密码

```mysql
alter user "USERNAME"@"%" identified by "NEW PSAAWORD";
```

给访问权限

```mysql
grant all privileges on *.* to root@'%' with grant option;
grant all privileges on db.table to user@'%' with grant option;
*.*表示 数据库.表
# 撤销权限
REVOKE privilege ON databasename.tablename FROM 'username'@'host';
REVOKE all ON information_schema.* FROM 'user'@'%';
REVOKE all ON p.* FROM 'user'@'%';
#刷新
flush privileges;
```

修改配置文件

```bash
sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf
#注释此行
#bind-address = 127.0.0.1

#在这里面也可以设置跳过验证登录
skip-grant-tables
```

修改完要重启mysql

```bash
service mysql restart
#检查状态
systemctl status mysql.service 
```



## python连接数据库

```powershell
#安装包
#mysql 5.0
pip install mysql-connector
#mysql 8.0
pip install MySQL-connector-python
```

```python
#导入包
import mysql.connector
#建立连接
mydb = mysql.connector.connect(
    host="google.com",  # 数据库主机地址
    user="user",  # 数据库用户名
    passwd="123456@WS"  # 数据库密码
)
```


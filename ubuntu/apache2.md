# apache2

## 基本配置

```
sudo apt install apache2 -y
```

-y表示确定安装yes

检查运行状态

```
systemctl status apache2
```

启动，停止，重启

```
sudo service apache2 start

sudo service apache2 stop

sudo service apache2 restart
```

配置文件


```
sudo vim /etc/apache2/ports.conf

sudo vim /etc/apache2/sites-available/000-default.conf

```

## 配置ssl

下载ssl证书文件，包括

1_root_bundle.crt    *# 证书文件* 

2_xxx.xxx.xxx.crt *# 证书文件* 

3_xxx.xxx.xxx.key *# 私钥文件*

创建ssl文件夹存放证书

```
sudo mkdir /etc/apache2/ssl
```

启动ssl

```
sudo a2enmod ssl
```

软链接`/etc/apache2/sites-available`中的两个文件到`/etc/apache2/sites-enabled`

```
ln -s /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-enabled/000-000-default.conf
ln -s /etc/apache2/sites-available/default-ssl.conf /etc/apache2/sites-enabled/000-default-ssl.conf
```

编辑`/etc/apache2/sites-available/default-ssl.conf`

```
ServerName ip

SSLCertificateFile /etc/apache2/ssl/2_xxx.xxx.xxx.crt
SSLCertificateKeyFile /etc/apache2/ssl/3_xxx.xxx.xxx.key
SSLCertificateChainFile /etc/apache2/ssl/1_root_bundle.crt
```

强制使用https

```
RewriteEngine on
RewriteCond %{HTTPS} !=on
RewriteRule ^(.*) https://%{SERVER_NAME}$1 [L,R]
```

启动重定向

```
sudo a2enmod rewrite
```


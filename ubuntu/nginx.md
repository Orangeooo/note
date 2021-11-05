# nginx

安装

sudo apt install nginx

启动

systemctl start nginx

自启动

systemctl enable nginx

配置文件位置

/etc/nginx/nginx.conf

一般在目录下新建一个文件夹，在里面新建配置文件，之后在nginx.conf里面添加

include /etc/nginx/conf/*.conf;

配置文件内容

```
server{
	listen    80;
	root /home/www/website;
	server_name ip;
	location /{
	}
}
```

在配置文件的root目录下建站


# nginx

安装

sudo apt install nginx

启动

systemctl start nginx

systemctl restart nginx

自启动

systemctl enable nginx

sudo systemctl disable nginx

重载

sudo systemctl reload nginx

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

ssl

```
server {
        listen 443 ssl;
        server_name www.domain.com; #填写绑定证书的域名
        ssl_certificate 1_www.domain.com_bundle.crt; #.crt文件路径
        ssl_certificate_key 2_www.domain.com.key;　#.key文件路径
        ssl_session_timeout 5m;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2; #按照这个协议配置
        ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:HIGH:!aNULL:!MD5:!RC4:!DHE;#按照这个套件配置
        ssl_prefer_server_ciphers on;
        location / {
            root   html; #站点目录
            index  index.html index.htm;
        }


```

```
server{
  listen 443;
  server_name [访问域名];
  ssl on;
  ssl_certificate [pem文件路径];
  ssl_certificate_key [key文件路径];
  ssl_session_timeout 5m;
  ssl_protocols SSLv2 SSLv3 TLSv1;
  ssl_ciphers ECDH:AESGCM:HIGH:!RC4:!DH:!MD5:!3DES:!aNULL:!eNULL;
  ssl_prefer_server_ciphers on;
  location / {
  proxy_pass [转发应用访问地址];
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Real-PORT $remote_port;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_redirect default;
  }
}
server {
  listen 80;
  server_name [访问域名];
  return 301 https://$server_name$request_uri;
}

```


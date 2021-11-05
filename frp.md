# frp

下载

### 服务端

```
wget https://github.com/fatedier/frp/releases/download/v0.37.1/frp_0.37.1_linux_amd64.tar.gz

tar -zxvf frp_0.37.1_linux_amd64.tar.gz

./frps -c ./frps.ini
nohup /path/to/your/fprs -c /path/to/your/frps.ini
nohup ./frps -c ./frps.ini
```

自启动

```
sudo vim /lib/systemd/system/frps.service
```



```
[Unit]
Description=fraps service
After=network.target syslog.target
Wants=network.target

[Service]
Type=simple
#启动服务的命令（此处写你的frps的实际安装目录）
ExecStart=/your/path/frps -c /your/path/frps.ini

[Install]
WantedBy=multi-user.target
```

启动

sudo systemctl start frps

开机启动

sudo systemctl enable frps

重启

sudo systemctl restart frps

停止

sudo systemctl stop frps

状态

sudo systemctl status frps

### 客户端

frpc.ini配置文件

```
[common]

server_addr = google.com
server_port = 7000
auto_token=qwertyuiop

[qwertyuiop1]

type = tcp
local_ip = 127.0.0.1
local_port = 3389
remote_port = 7777
```

启动脚本

```
@echo off
if "%1" == "h" goto begin
mshta vbscript:createobject("wscript.shell").run("""%~nx0"" h",0)(window.close)&&exit
:begin
cd C:\Program Files\frp\
frpc.exe -c frpc.ini
```


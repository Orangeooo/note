# ssh

Secure Shell

## 使用

ssh USER@IP

ssh root@192.168.1.1

## 免密登录

ssh-keygen -t rsa

在.ssh文件夹下生成以下两个文件

私钥：id_rsa    

公钥：id_rsa.pub

将公钥复制到远程主机的.ssh文件夹下的authorized_keys中



```undefined
配置文件
sudo vim /etc/ssh/sshd_config
重启
sudo service ssh restart
```

## 设置别名

.ssh/config文件

```
# ssh

Host ubuntu
    HostName g
    User ubuntu
    ServerAliveInterval 40  保持连接
```

## windows terminal设置别名

查看配置文件位置

```
$profile
```

前往目标位置创建文件，写入以下文字

如果别名不包含空格

```
Set-Alias -Name s -Value ssh
```

如果包含空格，使用function

```
Function sshubuntu {ssh ubuntu} 

Set-Alias -Name su -Value sshubuntu
```

```
get-ExecutionPolicy   # 查看系统执行策略状态

set-executionpolicy RemoteSigned # 修改执行策略状态
```

参考文档

https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/set-alias?view=powershell-7.1&viewFallbackFrom=powershell-6


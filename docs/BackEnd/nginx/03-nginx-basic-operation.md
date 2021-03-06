---
title: Nginx 基本操作
---

## 0. 进程与端口

### 进程

ps 是 `Process Status` 的简写，可以通过 ps 来查看对应的进程。

```bash
ps -ef | grep nginx
```

### 端口

netstat 是 `net status` 的简写， 可以查看有哪些端口正在被占用

```bash
netstat -tlnp
```

  


## 1. 启动

> 无法启动时增加 sudo

```bash
# 直接启动
nginx
# systemctl 启动
systemctl start nginx.service

# 开机启动
systemctl enable nginx.service
```

## 2. 停止

```bash
# normal quit
nginx -s quit
# force stop
nginx -s stop
# systemctl
systemctl stop nginx.service

# kill pid
killall nginx
## 或
kill -9 pid
```



## 3. 重启

```bash
# normal
nginx -s reload
# systemctl
systemctl restart nginx.service
```



## 4. 启用安全组

按照上方配置完是无法访问服务的，还需要进入阿里云去配置安全组，打开对应的端口才行。

操作流程：

`登录` > `控制台` > `云服务器ECS（左侧）` > `安全组` > `配置规则` > `添加安全组规则` > `填充内容` > `确定`
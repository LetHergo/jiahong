---
date: 2019-5-21
title: 初次使用nginx
categories:
  - 服务器
tags:
  - 服务器
  - nginx
---

# 初次使用 nginx

闲来无事想着腾讯云服务器买着吃灰好久了。。于是便诞生了这篇文章
服务器是 Centos 系统然后服务器选择的 nginx
主要是几个步骤

- yum install nginx -y
- nginx
  这时候可以访问 IP 看到测试页了

- 更改静态文件存储位置

```
vim /etc/nginx/nginx.conf
```

对啦 vim 我也是现学的编辑 保存退出=。=
把 root 更改为/data/www 后还有一个事情要处理 就是处理默认配置的一条注释掉
nginx.conf 配置文件中有一行是 include /etc/nginx/conf.d/\*.conf，把这行代码注释掉，保存退出，因为这行代码会使文件执行默认配置。

- 检查配置文件是否正确 nginx -t

- 在 data 目录下创建 www 文件夹 mkdir -p /data/www
- cd 到 www 文件夹下 创建 index.html 因为默认是访问 index.html
- 重启 nginx 命令是 nginx -s reload
  对了 有可能发生端口被多个 nginx 占用的情况 这时候请杀掉 nginx 再重新启动

---
layout: post
title: "docker-compose sql1"
data: 2021-03-08 10:33:00
categories: penetration
tags: tool docker ubuntu
excerpt: 高级攻防课程，主要安装docker-compose ，然后在此基础上进入sql1。遇到了一些问题，由此记录。
mathjax: true
author: Eurynome
---



## 本地搭建

### 1.解压缩

> sql.zip 解压缩，再拖到虚拟机里，Orz。



### ==2.启动容器==

```
curl -L https://github.com/docker/compose/releases/download/1.8.0/run.sh > /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

docker-compose --version
```

#### 遇到问题：

1. `bash: /usr/local/bin/docker-compose: Permission denied`

2. ERROR: Can't find a suitable configuration file in this directory or any parent. Are you in the right directory?

   ```
   Supported filenames: docker-compose.yml, docker-compose.yaml
   ```

3. ERROR: Network h1ve_frp_containers declared as external, but could not be found. Please create the network manually using `docker network create h1ve_frp_containers` and try again.

#### 解决办法：

1. 提升权限
2. 到相应yml的目录下操作
3. 修改配置

##### 提升权限

1. 直接在相应的命令前+`sudo`，但在此次实验中莫名失败了，所以采用第2种。
2. 直接使用管理者模式，或者超级管理者模式。

```
#管理者模式
sudo su

#超级管理者模式
sudo -i
```

##### 修改配置

1. 创建同名docker容器`docker network create h1ve_frp_containers`，然后继续`docker-compose up -d`
2. 将yml文件修改成自己创建的docker容器名

##### yml配置文件

> https://blog.csdn.net/qq_35720307/article/details/87256684
>
> https://blog.csdn.net/qq_24084605/article/details/89676502



### 3.配置成功

```
 ---> 222f03253435
Successfully built 222f03253435
Successfully tagged sql1:latest
Creating sql_service_1
```

***出现如上类似字段，则配置成功***。



### 4.本地访问

```
#访问网站
127.0.0.1:9999

#然后开始实验
```



## reference

https://www.yuque.com/docs/share/c0e29c66-15c0-41e6-8429-94ee7a41d712?#


---
layout: post
title: "penetration preparation"
data: 2021-03-02 15:55:00
categories: penetration
tags: tool sqlmap docker ubuntu
excerpt: 高级攻防课程的课前准备，主要配置环境，涉及ubuntu环境下安装sqlmap，docker等工具，并且在安装过程中遇到问题的解决总结。
mathjax: true
author: Eurynome
---

### 2. sqlmap

#### 2.1 是什么？

> SQLmap是一款用来检测与利用SQL注入漏洞的免费开源工具，有一个非常棒的特性，即对检测与利用的自动化处理（数据库指纹、访问底层文件系统、执行命令）。
> 官方网站下载http://sqlmap.org/



#### 2.2 安装

> Ubuntu20.04中已经安装python3.8

##### 2.2.1 git安装

```
sudo apt-get install git
```



##### 2.2.2 sqlmap

```
git clone git://github.com/sqlmapproject/sqlmap.git
```



##### ==2.2.3 软链接==

```
# 查看python3.8在哪个目录
whereis python3.8

#为python3.8创建软链接
sudo ln -s /usr/bin/python3.8 /usr/bin/python

#为sqlmap创建软链接
sudo ln -s sql安装目录/sqlmap.py /usr/bin/sqlmap
```

可能出现问题：

1. `ln: failed to create symbolic link '/usr/bin/sqlmap': Permission denied`  权限不够
2. `/usr/bin/env: ‘python’: No such file or directory`  无python指令

解决方案：

1. `sudo`
2. 找到python3.8目录，然后为python3.8创建软链接



##### 2.2.4 测试

```
sqlmap -h
```



###  3. docker

#### 3.1 是什么？

> Docker 是一个开源的应用容器引擎，基于 [Go 语言](https://www.runoob.com/go/go-tutorial.html) 并遵从 Apache2.0 协议开源。Docker 可以让开发者打包他们的应用以及依赖包到一个轻量级、可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。容器是完全使用沙箱机制，相互之间不会有任何接口（类似 iPhone 的 app）,更重要的是容器性能开销极低。



#### 3.2 安装

##### 3.2.1 安装curl

```
sudo apt install curl
```



##### 3.2.2 官方脚本自动安装

1. `curl -fsSL https://get.docker.com | bash -s docker --mirror Aliyun`
2. `curl -sSL https://get.daocloud.io/docker | sh`



##### 3.2.3 手动安装

> reference:https://www.runoob.com/docker/ubuntu-docker-install.html



#### 3.3 添加用户组

```
#将当前用户添加到docker用户组
sudo gpasswd -a ${USER} docker

#重新登陆或者用一下命令切换到docker组
newgrp - docker

#重启docke服务
sudo service docker restart
```



### 4. sqli-labs

#### 4.1 是什么？

> sql注入环境，可以利用docker安装。
>
> 当然，也可以在Windows本地安装，使用PHPstudy。



#### 4.2 安装

```
#查找sqli-labs 镜像
docker search sqli-lab

#拉取镜像到本地
docker pull acgpiano/sqli-labs

#运行
docker run -itdp 8000:80 acgpiano/sqli-labs
	-i:交互式操作
	-t:终端
	-p:将docker的端口映射到本地端口
	-d:后台
	
#退出
docker ps
docker stop 容器ID
```



## reference

https://www.yuque.com/docs/share/a8203c13-bd5c-4c1a-9d11-e263d5a99be2?#


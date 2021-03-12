---
layout: post
title: burpsuite抓取vmware上的数据包
data: 2021-03-12 14:08:00
categories: penetration
tags: ubuntu vmware burpsuite
excerpt: 如何使得本地burpsuite能够抓到虚拟机上的数据包，本次实验虚拟机：ubuntu20.04
mathjax: true
author: Euyrnome
---

[TOC]

## 本地burpsuite抓虚拟机包步骤

### 虚拟机设置

#### 1. 虚拟机将网络连接设置为NAT模式

>相当于主机虚拟出一个网卡，虚拟机单独成为一个网段，即虚拟机本身拥有可用网段。

在本地机命令行上输入`ipconfig`，VM1为桥接模式默认网卡，VM8为NAT模式默认网卡。

作者主要采用Firefox。



#### 2. 虚拟机选定的浏览器中安装FoxyProxy插件

1. 安装好插件后，选择`option`，在新加载的页面左侧选择`Add`
2. 在`Proxy IP address or DNS name`下填写VM8网段，`port`填写端口
3. 其余随意，最后`save`



#### 3. 虚拟机中设置浏览器连接

1. 菜单中选择`Preferences`，下拉至`Network Settings`
2. 点击`setting`
3. 在新页面中选择`Manual proxy congiguration`
4. `HTTP Proxy`中填写2.2中的网段及其端口号
5. ！！`No proxy for`中不要填写任何类似127.0.0.1或者localhost的网址



#### 4. 给浏览器安装burp证书

> 不知名原因，没法访问http://burp 网址，所以我就直接把本地机的证书拖到了虚拟机中。

1. 浏览器菜单栏选中`Preferences`以及`Privacy&Security`
2. 下拉至`Certificates`，并选中`View Certificates`
3. 将证书导入



### 本地机设置

> 前提条件，安装好burpsuite

1. 打开burpsuite，选择`Proxy`下`Option`
2. 选择`Proxy Listeners`的`Add`
3. 选择VM8网段，并绑定上面的端口，点击`OK`



### 配置好后遇到问题的解决

一切就绪后发现还是抓不到包，原因可能是**被防火墙拦截**了，所以此时我们可以把本地机的防火墙关闭，再次尝试。

成功抓包，来源为Ubuntu。

手机App等抓包与之类似。



## references

https://www.cnblogs.com/zjwoo/p/12772634.html

https://blog.csdn.net/kong_free/article/details/107343401








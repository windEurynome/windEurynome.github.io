---
layout: post
title: "how to know the linked wifi password"
data: 2021-03-05 22:25:00
categories: particular
tags: tool
excerpt: 查看已经连接的WIFI密码，记录用，经常忘记ORZ。
mathjax: true
author: Eurynome
---



### CMD指令查看WIFI密码

```
#打开CMD，以管理员身份运行
#列出所有连接过的WIFI配置文件
netsh wlan show profiles

#查看具体某个WIFI的配置文件
netsh wlan show profiles name = "XXX" key = clear
```

*PS:XXX为所连接的WIFI中的某个*



### 图形化界面查看WIFI密码

1. 打开`网络和Internet设置`
2. 点击`更改适配器设置`
3. 找到连接的WIFI，右击`状态`
4. 点击`无线属性`，并进入`安全`选项卡
5. 找到`网络安全密钥`，并勾选`显示字符`
6. 得到WIFI密码


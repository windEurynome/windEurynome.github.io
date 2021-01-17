---
layout: post
title: "how-to-import-to-VS"
categories: C++ VS
tags: VS tool
excerpt: VS如何调用第三方库，并对VS进行设置。
data: 2020-10-14 14:58:03
author: Eurynome
mathjax: true
---

# VS 如何调用第三方库
## 第三方库的构成
```
头文件，静态链接库，动态链接库
即：.h,.lib,.dll文件。
```

## 如何使用
### 步骤一：拷贝文件夹
1. 将include文件夹拷贝进VS项目
2. 将lib文件夹拷贝进VS项目中

### 步骤二：进行VS项目配置
1. 右键项目，属性->配置属性->C/C++->常规，在常规中找到附加包含目录，写上include，即拷贝后项目下的include文件夹。
2. 属性->配置属性->链接器->常规，在常规中找到附加库目录，写上lib，即拷贝后项目下的lib文件夹。

## 遇到问题的解决方法




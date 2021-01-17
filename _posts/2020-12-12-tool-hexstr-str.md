---
layout: post
title: "hexstr2str"
categories: convert python
tags: tool
excerpt: the conversion of hexstr to str
data: 2020-12-12 21:30:00
mathjax: true
author: Eurynome
---

# 十六进制转和字符串之间的转化
## 十六进制到字符串

```python
#!/usr/bin python3
#-*-coding=utf-8-*-
import binascii

#若传入的是一连串16进制串，可用以下函数
def hex_to_str1(s):	#s="68656c6c6f"
	s=binascii.unhexlify(s) #unhexlify()传入的参数也可以是b'xxxx'(xxxx要符合16进制特征)
	print(s.decode('utf-8')) #s的类型是bytes类型，用encode()方法转化为str类型

#若传入的是用空格隔开的16进制串，可以用一下函数
def hex_to_str2(s): #s="68 65 6c 6c 6f"
    print("".join([chr(i) for i in [int(b,16) for b in s.split(' ')]])) 

12345678910111213
```

## 字符串到十六进制

```python
#!/usr/bin python3
#-*-coding=utf-8-*-
import binascii

#若传入的是二进制串，可用以下函数
def str_to_hex1(s):	#s=b'hello'
	s=binascii.hexlify(s) #unhexlify()传入的参数也可以是b'xxxx'(xxxx要符合16进制特征)
	print(s.decode('utf-8')) #s的类型是bytes类型，用encode()方法转化为str类型

#若传入的是文本串，可以用一下函数
def str_to_hex2(s): #s="hello"
    print("".join([hex(ord(c)).replace('0x','') for c in s]))
123456789101112
```
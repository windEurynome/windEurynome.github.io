---
layout: post
title: "buuoj,密码学的心声&Unencode"
categories: crypto python
tags: ASCII UUENCODE buuoj
excerpt: buuoj刷题wp,本文章关于ASCII码进制转换和UUENCODE编码方式。
data: 2020-07-05 23:00:00
author: Eurynome
mathjax: true
---

# 密码学的心声
## 题目
  二战时期，某国军官与一个音乐家情妇相好，然而自从那时起，他屡战屡败，敌人似乎料事如神。他也有怀疑过他的情妇，但是他经过24小时观察他的情妇，发现她每天都只是作曲，然后弹奏给战地电台，为士兵们鼓气，并未有任何逾越。那么，间谍到底是谁？这张曲谱是否有猫腻？ (答案为一个明文字符串，提交获得的有意义语句通顺字符串即可) 注意：得到的 flag 请包上 flag{} 提交。
  “111114157166145123145143165162151164171126145162171115165143150”
  （啊啊啊啊啊，我就是密码，啊啊啊啊啊，我的生命很奇葩。如果说你不认识简谱，那也别怕，不需要奏唱出来，请转换成埃塞克码。也许你奇怪，我转出来的是啥，你仔细看看，这里面没有八，你肯定以为是十进制，其实简单的啦。）

## 分析
```
1. 关于ASCII码
2. 没有8，所以考虑八进制
3. 进制转换
```

## 解题
1. 先把上述数字按照3个一组进行分组
2. 利用解密网站：https://www.sojson.com/hexconvert/8to10.html （8进制转换成10进制）
3. 把转换过后的10进制数对应的ASCII码解出
4. 最后依次可得到：ILoveSecurityVeryMuch

## 获得flag
```
flag{ILoveSecurityVeryMuch}
```

#### 一点思考
  **解读题意，进制转换**，看到没有8，往8进制想，后转换成10进制再考虑ASCII码。


# UNENCODE
## 题目
  89FQA9WMD<V1A<V1S83DY.#<W3$Q,2TM]

## 分析
  搜索相关，发现有种加密为“UUENCODE”，查询定义，得：
```
  uuencode是将二进制文件转换为文本文件的过程，转换后的文件可以通过纯文本e-mail进行传输，在接收方对该文件进行uudecode，即将其转换为初始的二进制文件。
  uu 编码:uuencode 编码方式用于将任意的二进制文件转换为文本文件，比如email.转换后的文件中仅包含可打印字符·
  uuencode 运算法则将连续的 3字节编码转换成 4字节（8-bit 到 6-bit）的可打印字符· 该编码的效率高于Hex 格式
```
## 解题
  直接解密网站破解：http://ctf.ssleye.com/uu.html

## 获得flag
```
flag{dsdasdsa99877LLLKK}
```

#### 一点思考
  难点主要在于**能不能看出是UUENCODE编码**。

  



---
layout: post
title: "buuoj-MRCTF2020-keyboard"
categories: crypto python
tags: buuoj keyboard MRCTF2020
excerpt: buuoj刷题wp，本文章关于9键的数字和字母组合。
data: 2020-08-01
author: Eurynome
mathjax: true
---

# [MRCTF2020]keyboard
## 题目
https://buuoj.cn/challenges#[MRCTF2020]keyboard

得到的flag用
MRCTF{xxxxxx}形式上叫
都为小写字母

6
666
22
444
555
33
7
44
666
66
3

## 分析
刚看到数字，且没有1，判断和9宫格有关。
但，使用九宫格后，发现汉字与输入法习惯有关，有挺大的不确定性。
所以，直接考虑了对应的字母，如6键1为m,2为n，3为o。

## 解题
打开9宫格输入法，然后对应解出。

## 得到flag
```
flag{mobilephone}
```

#### 一点思考
认准方向，变换思考。
跟实际生活相结合。
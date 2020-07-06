---
layout: post
title: "buuoj,rot"
categories: crypto
tags: buuoj rot hash
excerpt: buuoj刷题wp，本文章关于ROT移位加解密和关于MD5的hash碰撞。
data: 2020-07-06 23:29:36
author: Eurynome
mathjax: true
---

# rot
## 题目
  破解下面的密文：

83 89 78 84 45 86 96 45 115 121 110 116 136 132 132 132 108 128 117 118 134 110 123 111 110 127 108 112 124 122 108 118 128 108 131 114 127 134 108 116 124 124 113 108 76 76 76 76 138 23 90 81 66 71 64 69 114 65 112 64 66 63 69 61 70 114 62 66 61 62 69 67 70 63 61 110 110 112 64 68 62 70 61 112 111 112

  flag格式flag{}

## 分析
1. 题目为rot，就考虑rot移位加解密
2. 跑代码出来后发现，有部分未知字符，以及md5，考虑hash碰撞
3. 再次跑代码，跑出最后结果

## 解题
1. rot移位加解密，代码如下：
```
a="83 89 78 84 45 86 96 45 115 121 110 116 136 132 132 132 108 128 117 118 134 110 123 111 110 127 108 112 124 122 108 118 128 108 131 114 127 134 108 116 124 124 113 108 76 76 76 76 138 23 90 81 66 71 64 69 114 65 112 64 66 63 69 61 70 114 62 66 61 62 69 67 70 63 61 110 110 112 64 68 62 70 61 112 111 112"
b=a.split(" ")
m="38e4c352809e150186920aac37190cbc"
flag=""
for j in range(0,26):
    flag=""
    for i in range(len(b)):
        flag+=chr(int(b[i])-j)
    print(flag)
```

求得：
```
FLAG IS flag{www_shiyanbar_com_is_very_good_????}
MD5:38e4c352809e150186920aac37190cbc
```

2. 关于MD5的hash碰撞，代码如下:

```
import hashlib
a="83 89 78 84 45 86 96 45 115 121 110 116 136 132 132 132 108 128 117 118 134 110 123 111 110 127 108 112 124 122 108 118 128 108 131 114 127 134 108 116 124 124 113 108 76 76 76 76 138 23 90 81 66 71 64 69 114 65 112 64 66 63 69 61 70 114 62 66 61 62 69 67 70 63 61 110 110 112 64 68 62 70 61 112 111 112"
b=a.split(" ")
m="38e4c352809e150186920aac37190cbc"
# flag=""
# for j in range(0,26):
#     flag=""
#     for i in range(len(b)):
#         flag+=chr(int(b[i])-j)
#     print(flag)
flag="flag{www_shiyanbar_com_is_very_good_"

for x in range(21,127):
    for y in range(21,127):
        for z in range(21,127):
            for q in range(21,127):
                w=hashlib.md5(str(flag + chr(x) + chr(y) + chr(z) + chr(q) + "}").encode("utf-8"))
                w0=w.hexdigest()
                print(w0)
                if(w0==m):
                    print(flag+chr(x)+chr(y)+chr(z)+chr(q)+"}")
                    break
```

## 获得flag
```
flag{www_shiyanbar_com_is_very_good_@8Mu}
```

#### 一点思考
1. python脚本
2. 未知字符的关于MD5的hash碰撞
3. 1中脚本的m值是事先知晓的吗？



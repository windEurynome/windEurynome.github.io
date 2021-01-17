---
layout: post
title: "RSA-attack"
categories: crypto RSA attack python
tags: RSA attack
excerpt: buuoj做题的wp，本文章关于RSA的所有攻击模式（应该），后续会把做过的RSA题目分门别类整理。
data: 2020-08-01
mathjax: true
---

## RSA选择密文攻击：
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_chosen_cipher/
#### 任意密文解密 
#### RSA parity oracle 


## RSA复杂题目
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_complex/
#### 2016 ASIS Find the flag 
#### SCTF RSA1 
#### 2018 WCTF RSA 


## Coppersmith 相关攻击
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_coppersmith_attack/
#### Basic Broadcast Attack 
#### Broadcast Attack with Linear Padding 
#### Related Message Attack 
#### Coppersmith’s short-pad attack 
#### Known High Bits Message Attack 
#### Factoring with High Bits Known 
#### Boneh and Durfee attack 


## Rsa d attack
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_d_attack/
#### d 泄露攻击 
#### Wiener's Attack 
#### 综合例子 

## Rsa e attack
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_e_attack/
#### 小公钥指数攻击 



#### RSA 衍生算法——Rabin 算法 




## Rsa module attack
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_module_attack/
#### 暴力分解 N 
```
在 N 的比特位数小于 512 的时候，可以采用大整数分解的策略获取 p 和 q。
```

#### p & q 不当分解 N 
```
当 RSA 中 p 和 q 选取不当时，我们也可以进行攻击。
```

#### 模不互素  
```
当存在两个公钥的 N 不互素时，我们显然可以直接对这两个数求最大公因数，然后直接获得 p，q，进而获得相应的私钥。
```

#### 共模攻击 
```
当两个用户使用相同的模数 N、不同的私钥时，加密同一明文消息时即存在共模攻击。
```


## Bleichenbacher's attack
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_pkcs_attack/
#### PKCS 1.5 标准中可以伪造 RSA 签名


## RSA 侧信道攻击
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_side_channel/
#### 侧信道



## RSA 介绍
https://wiki.x10sec.org/crypto/asymmetric/rsa/rsa_theory/

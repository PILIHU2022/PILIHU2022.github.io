---
title: 提取Cloudflare Zero Trust节点
date: 2024-02-06 14:07:46
tags: Cloudflare
categories: 白嫖
---
# 本文记录作者提取Cloudflare Zero Trust的节点的过程以及所用的工具

# 开始
首先需要你有一个Cloudflare账号，并且有Zero Trust，没有可以看[这篇文章](https://blog-zjp.cn.eu.org/Request-Cloudflare-Warp/)

# 开始操作
## 首先介绍一下作者的设备：
- OS:Arch Linux
- 内核:linux-zen6.7.3
- Clash-meta 1.18.1-2\
由于Cloudflare Zero Trust是使用WireGuard协议，所以我们需要使用一个支持WireGuard协议的客户端，可以更换为其他的\
本文以Arch Linux为例
## 首先
介绍一下作者提取节点时所用到的工具：
- [Warp2Clash by CMLiussss](https://gitlab.com/PILIHU/Warp2Clash)
- [优选IP脚本 by MisakaNo](https://gitlab.com/Misaka-blog/warp-script/)
- [提取`PrivateKey`和`PublicKey`的工具 by MisakaNo(WGCF)](https://replit.com/@misaka-blog/wgcf-profile-generator)\
或
- [提取`PrivateKey`和`PublicKey`的工具 by MisakaNo(Warp-go)](https://replit.com/@misaka-blog/warpgo-profile-generator)
## 开始操作
首先你需要提取出来你的Zero Trust的`PrivateKey`和`PublicKey`，没有的话[可以看这里](#首先)\
将Warp2Clash脚本下载下来：
```
wget -N -P Warp2Clash https://raw.githubusercontent.com/cmliu/Warp2Clash/main/W2C_start.sh && cd Warp2Clash && chmod +x W2C_start.sh
```
### 若你有WARP账户许可证密钥，可以使用以下命令：
```
./W2C_start.sh {WARP账户许可证密钥}
```
### 如果你有`PrivateKey`和`PublicKey`的话可以使用以下命令：
```
./W2C_start.sh {PrivateKey} {PublicKey} {IPv6}
```
<mark>注意：这个{IPv6}是必须要有的，否则将不会生成clash订阅文件！</mark>
### 获取`PrivateKey`和`PublicKey`
首先打开[提取工具](https://replit.com/@misaka-blog/wgcf-profile-generator)，

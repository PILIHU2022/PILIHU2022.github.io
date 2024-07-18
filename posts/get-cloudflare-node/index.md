# 提取Cloudflare Zero Trust节点

# 本文记录作者提取Cloudflare Zero Trust的节点的过程以及所用的工具

# 开始
首先需要你有一个Cloudflare账号，并且有Zero Trust，没有可以看[这篇文章](https://blog-zjp.cn.eu.org/Request-Cloudflare-Warp/)

# 开始操作
## 首先介绍一下作者的设备：
- OS:Arch Linux
- 内核:linux-zen6.7.3
- Clash-meta 1.18.1-2

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
wget -N -P Warp2Clash https://raw.githubusercontent.com/cmliu/Warp2Clash/main/W2C_start.sh &amp;&amp; cd Warp2Clash &amp;&amp; chmod &#43;x W2C_start.sh
```
### 若你有WARP账户许可证密钥，可以使用以下命令：
```
./W2C_start.sh {WARP账户许可证密钥}
```
### 如果你有`PrivateKey`和`PublicKey`的话可以使用以下命令：
```
./W2C_start.sh {PrivateKey} {PublicKey} {IPv6}
```
&lt;!-- &lt;mark&gt;注意：这个{IPv6}是必须要有的，否则将不会生成clash订阅文件！&lt;/mark&gt; --&gt;
### 获取`PrivateKey`和`PublicKey`
#### 首先打开[提取工具](https://replit.com/@misaka-blog/wgcf-profile-generator)，然后按照提示填写，Zero Trust用户选择“3”，然后访问网站并且将token复制到控制台回车，然后等待即可获取到`PrivateKey`和`PublicKey`，保留备用
#### 优选IP，将[优选IP脚本](https://gitlab.com/Misaka-blog/warp-script/)下载下来：
```
wget -N https://gitlab.com/Misaka-blog/warp-script/-/raw/main/files/warp-yxip/warp-yxip.sh
```
然后为脚本添加运行权限：
```
chmod &#43;x ./warp-yxip.sh
```
然后执行脚本：
```
./warp-yxip.sh
```
在菜单中输入2并且回车，等待执行结果出来以后将列表中的第一个中&#34;[]&#34;中的IP地址即可\
&lt;mark&gt;注意：这必须要在断开梯子以后才能执行！否则会导致测试结果不准确或者无效！&lt;/mark&gt;
#### 到刚刚下载的Warp2Clash目录，运行脚本：
```
./W2C_start.sh {PrivateKey} {PublicKey} {IPv6}
```
此处的“{PrivateKey} {PublicKey}”是之前获取到的；{IPv6}是刚刚优选出来的IPv6。
#### 最终会打印出成功字样的语句，并且将文件保存到Warp2clash.yaml中。
### 操作结束
### 若想导入到Clash-meta中，可以将文件放进/etc/clash-meta中，也可以自定义存放路径，记住就好。
然后编辑/etc/clash-meta/config.yaml：
在`proxy-providers`中添加以下内容：
```
  name:
      type: file
      path: /path/to/Warp2Clash.yaml
      health-check:
        enable: true
        interval: 36000
        url: https://cp.cloudflare.com/generate_204
```
&lt;mark&gt;记住要缩进！&lt;/mark&gt;
&lt;mark&gt;记住在groups中启用该配置&lt;/mark&gt;
## 然后使用以下命令检查配置是否正确：
```
clash-meta -t -d /path/to/clash-meta # 这里的路径要是clash-meta的配置文件所在路径不需要加入文件名
```
# 重载配置文件即可使用


---

> 作者: PILIHU(Spark)  
> URL: https://pilihu2022.github.io/posts/get-cloudflare-node/  


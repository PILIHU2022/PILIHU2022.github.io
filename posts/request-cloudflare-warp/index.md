# 免信用卡申请Cloudflare Zero Trust

# 客户端们
Android：[Cloudflare One Agent](https://pilihu2023-my.sharepoint.com/:u:/g/personal/pilihu_pilihu2023_onmicrosoft_com/ERwqnqCENdpNu3lZDh2Yf24BG8JUk3J1-2PYzGyJgIMIBg?e=eLDgjg)
Windows；macOS；Linux等见[官网](https://1.1.1.1/)
官方说明了在iOS和Android下使用Zero Trust的必须切换为Cloudflare One Agent，而Windows；macOS；Linux则不需要操作：
&gt; macOS, Windows, and Linux
No action is required for desktop clients at this time. The existing Cloudflare WARP client will continue to support both Zero Trust and 1.1.1.1 functionality.
&gt; ​​iOS and Android
Zero Trust users must migrate from the 1.1.1.1 app to the Cloudflare One Agent app by 2023-12-31.
Organizations can migrate their teams with minimal disruption in one of two modes: manually or via a managed endpoint solution.
Migration impact
&gt;   - New Zero Trust features will only be released to the Cloudflare One Agent.
&gt;   - The 1.1.1.1 app will continue to support the current feature set (and any security updates) through 2023-12-31.
&gt;   - All Zero Trust functionality will be removed from 1.1.1.1 app versions released after 2023-12-31. Zero Trust will continue to work on 1.1.1.1 app versions released prior to 2023-12-31.

# 视频教程
## YouTube
https://youtu.be/5XMrQEPgY88?si=dv1ADYJ5OlfZqH38
https://youtu.be/XkKt8LDhDQk?si=vmXVaxbyfgXIAEof

## 搬运
https://pilihu2023-my.sharepoint.com/:f:/g/personal/pilihu_pilihu2023_onmicrosoft_com/EoP43Tll21ZKk2zShIcUZfgBlHp-4um5zLgCsa5PZd02Pw

# 开始实际操作
1. 打开[Cloudflare官网](https://www.cloudflare-cn.com/)登录，若无账号可以注册，不需要特殊手段，QQ邮箱即可
2. 点击菜单中的Zero Trust
3. 在输入框中输入你想要的组织名
4. 选择计划，免费即可，若有特殊需求可以选择其他的，在‘Free’一栏中点击select plan
5. 点击proceed to payment
6. 点击‘add payment method’
7. 等待页面完全加载完后关闭标签页（选择付费计划的需添加）
8. 打开[Cloudflare官网](https://www.cloudflare-cn.com/)重新登录，再打开Zero Trust就可以进入了
9. 侧边栏选择‘My Team’
- ~~不出意外的话应该会出意外~~，会没有提示添加设备，不要慌张，点击‘My Team’ -&gt; ‘List’，再回到刚刚的页面，即可看见
![Cloudflare Zero Trust连接客户端](https://s1.imagehub.cc/images/2024/01/17/79ae12aeae61a4d7541db018dd92130f.png)]
10. 点击‘connect a device’
11. 点击‘create a device enrollment policy’
12. 在输入框中输入邮箱地址后缀，如‘@qq.com’等
# 在已安装的客户端中输入你的地址，为‘*.cloudflareaccess.com’，我们只需要填写‘*’即可
&lt;mark&gt;注：此处的‘*’指你起的团队名称&lt;/mark&gt;
# 在弹出的页面中输入你自己的邮箱（要真实邮箱，用于接受验证码）
# 在邮箱中复制验证码填写即可
# The end

---

> 作者: PILIHU(Spark)  
> URL: https://pilihu2022.github.io/posts/request-cloudflare-warp/  


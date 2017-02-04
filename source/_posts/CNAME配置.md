---
title: github CNAME 设置
tags: github
date: 2017/2/3
categories: 技术
---
每次提交页面到githubpage上后总是受到一封警告邮件，虽说不影响访问但是被骚扰的很烦，(github的好意实在是太频繁了)
<!-- more -->
>The page build completed successfully, but returned the following warning:
**Your site's DNS settings are using a custom subdomain, www.wenfanchao.win, that's set up as an A record. We recommend you change this to a CNAME record pointing at wenfanchao.github.io.** For more information, see https://help.github.com/pages/.
For information on troubleshooting Jekyll see:
https://help.github.com/articles/troubleshooting-jekyll-builds

有用的核心就是高亮的那句，意思很明确你的域名没有指向一个正确的地址
## 解决办法
1. 首先在hexo的suorce中增加CNAME文件，内容就是你购买的域名
```
www.wenfanchao.win
```
2. 然后就在万网控制台修改A记录地址并增加CNAME
![cnamepig](http://oktra8f0g.bkt.clouddn.com/image/png/cnamepag.png)
CNAME的值就是你githubpage地址:wenfanchao.github.io
3. 使用dig命令获取A记录的值
``` bash
dig wenfanchao.github.io +nostats +nocomments +nocmd
```
注意wenfanchao.github.io为你博客的地址。
4. windows安装dig</br>到百度云盘下载如下dig工具地址：链接：http://pan.baidu.com/s/1gedd9WB 密码：wtr3</br>
安装完毕后在环境变量中添加就能使用了

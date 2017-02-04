---
title: hexo模板之ejs与Swig的优劣
tags: hexo
date: 2017/2/2
categories: 技术
---
## 2个模板
hexo刚入坑，随便从网上down了2个themes一个next，一个freemind
<!-- more -->

简单说一下认识[ejs](http://www.embeddedjs.com/)比[swig](https://github.com/paularmstrong/swig)语法更丰富当然这和2个模板的定位不一样,但是对我这种懒人来说EJS更好用为啥就举例一个

ejs
```
site.tags.random().limit(20)
```
swig没有直接导致我要随机输出标签的功能完蛋。

swig只能老实的
```
{% for item in site.tags %}
  <li><a href="{{config.root}}{{item.path}}">{{item.name}}<span>{{item.posts.length}}</span></a></li>
{% endfor %}
```

---
title: hexo+githubpage安装配置
tags: hexo
date: 2017/2/3
categories: 技术
---
最近终于用hexo+githubpage把个人博客建立了，中间遇到不少的坑，记下来省的再犯。
<!-- more -->

## githubpage

### githubpage真的是个好项目，为我们广大屌丝解决了很多问题
具体的不想详细介绍不管是度娘还是谷哥都是一大堆。就给个地址: **[githubpage](https://pages.github.com)**


## hexo

### hexo也没啥说的官网巨详细基本就是照着做就可以
地址:
**[hexo](https://hexo.io)**

### themes
hexo的社区很活跃提供的样式也很多这里选择了 **[next](http://theme-next.iissnan.com)** 这个被加星最多的样式，感觉还是很不错的该有的功能一应俱全
#### next
next 主题功能全面，这里我只把个人修改的地方做个介绍
1. 我修改了主题里的footer模板，原因是我对HEXO强力驱动和next主题支持这个标签实在是无爱了</br>
footer模板位置：themes\next\layout\_partials\footer.swig
</br>模板很容易看懂，修改自己需要的内容就可以了。
</br>ps:注意里面变量的值是从你设置的对应语言的YML中获取的，我设置的简体中文。文件位置在themes/next/languages/zh-Hans.yml
2. next的标签页面我不太喜欢，或者说是hexo的tagcloud样子我觉得都不是太爱。所以修改了样式，参考了[freemind](http://wzpan.github.io/hexo-theme-freemind/)的标签样式
3. 修改模板 themes\next\page.swig </br>
替换了原有的标签生成修改为自定的 div与样式
```
<div id="posts" class="posts-expand">
{% include '_partials/page-header.swig' %}
  {# tagcloud page support #}
  {% if page.type === "tags" %}
    <div class="tag-cloud">
      <div class="tag-cloud-title">
          {{ _p('counter.tag_cloud', site.tags.length) }}
      </div>
      <div class="widget">
        <ul class="tag_box inline list-unstyled">
        {% for item in site.tags %}
          <li><a href="{{config.root}}{{item.path}}">{{item.name}}<span>{{item.posts.length}}</span></a></li>
        {% endfor %}
        </ul>
      </div>
    </div>
```

4. 修改样式 themes\next\source\css\_common\components\post\post-tags.styl
中增加
``` css
.widget {
  padding-bottom: 25px;
  border-bottom: 1px solid #e0e0e0;
}
.tag_box {
  margin:0;
  overflow:hidden;
}
.tag_box li {
  line-height:28px;
}
.tag_box li i {
  opacity:0.9;
}
.tag_box.inline li {
  float:left;
}
.tag_box a {
  padding: 2px 6px;
  margin: 2px;
  background: #e5e5e5;
  color:#555;
  border-radius: 3px;
  text-decoration:none;
  border:1px dashed #bbb;
}
.tag_box a span{
  vertical-align:super;
  font-size:0.8em;
}
.tag_box a:hover {
  background-color:#397bdd;
  color:#FFF;
}
.tag_box a.active {
  background:#57A957;
  border:1px solid #4C964D;
  color:#FFF;
}
```

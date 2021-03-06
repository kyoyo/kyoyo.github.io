---
layout: post
title: Resource List
category: 常用
tags: Resource List
keywords: 
description: 
---

# 修改双系统（win10+ubuntu）启动顺序和启动时间

安装了ubuntu16.04后，GNU GRUB引导的默认启动项是ubuntu，如果希望默认启动项是windows，修改方法如下：

step1. 进入Ubuntu系统，打开终端，输入  sudo gedit  /etc/default/grub；
step2. 打开grub文件以后，第一行代码为 GRUB_DEFAULT=0（以#开头的是注释行，不算代码），意思就是启动菜单顶部的为默认启动项，将0改为4，保存，退出。（启动菜单中一般共五项，windows位于最后，我的ubuntu16.04 +win10是这样的。）      默认启动时间是10s，可以这样修改：在GRUB_DEFAULT=0这一行下面2、3行的样子，有一行代码是GRUB_TIMEOUT=10，修改数字，保存，退出。（千万别忘了执行第三步，更新grub文件）
step3. 然后在终端中输入 sudo update-grub，也就是更新grub.cfg文件，使刚才的改动生效。


重启电脑，应该就修改成功了。


# 非常优秀的函数图形软件
  https://www.geogebra.org/
# amazeui
  http://amazeui.org/
  中国首个开源 HTML5 跨屏前端框架

# Layoutlt
很好用的网页布局设计工具

# Antetype
网页设计神器

# SSH工具
RLogin 好用的命令工具
http://nanno.dip.jp/softlib/man/rlogin/

# 数据库工具
A5:SQL MK-2 好用的开源数据库工具
http://forest.watch.impress.co.jp/library/software/a5sqlmk2/

# Django 博客系统教程
http://cdn2.jianshu.io/p/a822b479106a

# javascript网站
https://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000

- w3schools
  https://www.w3schools.com/js/
  
# Ajax实现购物车
http://blog.csdn.net/darkangel1228/article/details/53605948

# Hexo
Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，
在几秒内，即可利用靓丽的主题生成静态网页。

知乎讨论Hexo
https://www.zhihu.com/question/24422335

# 网上商城数据表
http://www.wstmart.net/database-952.html

# 国内外代码托管品台

http://www.jianshu.com/p/bd24f3202011
# Github
很多人搜索github，但是芸芸众生，要找到自己想要的项目犹如海底捞针一般，今天教大家几项神技，可以快速找到自己想要的内容。

1. 按star数目搜索，比如JavaScript，要求星数，这样就能获取star数目最多的项目

2. follow一些github上面的大牛

   请登录：https://github-ranking.com/

   国内大牛：http://outofmemory.cn/github/

   这里是搜索名人的网址：https://github.com/search

   高级搜索：https://github.com/search/advanced

3. Awesome + 你的关键字：搜索一些优秀的框架、教程、项目等

4. 看一些搜索技巧，设定条件进行搜索

   地址：https://help.github.com/articles/searching-repositories/


5. 通过readme看看人家是否发出pull request

   看看这篇文章：http://blog.csdn.net/qianlong4526888/article/details/11529981


6. 看explore推荐

   https://github.com/explore


7. 看看其他

   http://blog.sina.com.cn/s/blog_4e60b09d0102vcso.html


8. 直接github上搜fackbook或者其他，可以看到他们的最新作品


# Github代码搜索技巧

## 指定搜索方式

http://robbiefeng.iteye.com/blog/2169967
 
- octocat in:file
   
  搜索文件中有octocat的代码
    
- octocat in:path
    
  搜索路径中有octocat的代码
    
- octocat in:file,path
    
  搜索路径中有octocat的代码或者文件中有octocat的代码
    
- display language:scss
    
  搜索用scss写的包含display的代码
    
- Integer
    
  搜索包含Integer的字段
    

## 通过语言搜索代码

- element language:xml size:100

  搜索大小为100字节的xml代码
    
- user:mozilla language:markdown

  搜索mozilla用户下用markdown写的代码


- android language:java fork:true

  搜索用java写的 android相关的代码并且被fork过


- function size:>10000 language:python

  搜索与function相关的python代码，文件大小超过10kb


## 按照目录结构搜索

- console path:app/public language:javascript

  在app/public directory目录下搜索console关键字

- form path:cgi-bin language:perl

  搜索cgi-bin目录下包含form的perl代码


## 通过文件名搜索

- filename:.vimrc commands

  搜索 文件名匹配*.vimrc* 并且包含commands的代码

- minitest filename:test_helper path:test language:ruby

  在test目录中搜索包含minitest且文件名匹配"*test_helper*"的代码


## 根据扩展名来搜索代码

- form path:cgi-bin extension:pm

  搜索cgi-bin目录下以pm为扩展名的代码
    
- icon size:>200000 extension:css

  搜索超过200kb包含icon的css代码


## 通过用户或者组织来查找

- user:github extension:rb

  查找github用户中以rb为扩展的代码
    
- repo:mozilla/shumway extension:as

  搜索mozilla的shumway以as为扩展的代码

## Android 开发

现在很多App里都内置了Web网页（Hyprid App），这是Android里一个叫WebView的组件实现的
https://www.jianshu.com/p/3c94ae673e2a

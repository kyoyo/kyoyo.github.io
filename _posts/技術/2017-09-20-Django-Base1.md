---
layout: post
title: Django基础
category: 技术
tags: Django
keywords: 
description: 
---

开发环境准备

```
#安装python

#安装django
pip3 install -v django==1.10.7

#创建virtualenv
virtualenv django-env

#激活virtualenv
.\django-env\Scripts\activate.bat

#创建新工程
django-admin.py startproject MyBlog

#创建app
python manage.py startapp article

#start web server
manage.py runserver

#同步生成DB 仅在第一次用
python manage.py migrate

#之后编辑model后，都要执行这两个
python manage.py makemigrations
python manage.py migrate

#创建超级用户
python manage.py createsuperuser

#python交互环境变量设置
import os
import django
os.environ.setdefault("DJANGO_SETTINGS_MODULE", "MyBlog.settings")
django.setup()

#settings


```


The view layer
```
#urls lib
from django.conf.urls import url,include
url(r'^$', views.IndexView.as_view(), name='index')

#regrex
(?P<year>\d+) group匹配

* 匹配前一个字符0次或无限次
+ 匹配前一个字符1次或无限次
? 匹配前一个字符0次或1次
\d 数字[0-9]
\s 空白字符
\S 非空白字符
\w 单词字符[A-Za-z0-9_]

#views lib
from django.http import HttpResponse
from django.views import generic

#paginator
context = {
                'paginator': paginator,
                'page_obj': page,
                'is_paginated': is_paginated,
                'object_list': queryset
}


#admin
from django.contrib import admin
admin.site.register(Article)


#tag
from django import template
from django.template.defaultfilters import stringfilter
from django.conf import settings

register = template.Library()

@register.simple_tag
@register.inclusion_tag('blog/tags/breadcrumb.html')

@register.filter(is_safe=True)
@stringfilter


#setting
  #TEMPLATES
  TEMPLATES 'DIRS': [os.path.join(BASE_DIR, 'templates')]

  #auth
  AUTH_USER_MODEL='auth.User'

  # Static files (CSS, JavaScript, Images)
  STATICFILES = os.path.join(BASE_DIR, 'static')
```

errors 
'''
#error1
error:Add or change a related_name argument to the definition for 'BlogUser.groups' or 'User.groups'.
solution:AUTH_USER_MODEL='accounts.BlogUser'

#error2
error:django makemigrations no changes detected
solution:python manage.py makemigrations --empty yourappname 生成一个空的initial.py
'''

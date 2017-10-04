---
layout: post
title: Django基础
category: 技术
tags: Django
keywords: 
description: 
---

## 开发环境准备

```
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

## database sqlite3 
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'MyBlog.db'),
    }
}

## Static files (CSS, JavaScript, Images)
  STATICFILES = os.path.join(BASE_DIR, 'static')

```


## The view layer

### libs
```
#views lib
from django.shortcuts import render
from django.http import HttpResponse
from django.views.generic.list import ListView
from django.views.generic.detail import DetailView
from django.conf import settings

#urls lib
from django.conf.urls import url,include

#forms lib
from django import forms
from django.forms import ModelForm
from django.contrib.auth.models import User
from django.contrib.auth import get_user_model
```
### urls
```
#eg.
url(r'^$', views.IndexView.as_view(), name='index')
url(r'^page/(?P<page>\d+)$', views.IndexView.as_view(), name='index_page'),
url(r'^article/(?P<year>\d+)/(?P<month>\d+)/(?P<day>\d+)/(?P<article_id>\d+).html$',
        views.ArticleDetailView.as_view(),
        name='detail'),
url(r'^category/(?P<category_name>\S+).html$',views.CategoryDetailView.as_view(),name='category_detail'

#regrex
(?P<year>\d+) group匹配

* 匹配前一个字符0次或无限次
+ 匹配前一个字符1次或无限次
? 匹配前一个字符0次或1次
\d 数字[0-9]
\s 空白字符
\S 非空白字符
\w 单词字符[A-Za-z0-9_]


```
### paginator
```
url(r'^page/(?P<page>\d+)$', views.IndexView.as_view(), name='index_page'),
context = {
                'paginator': paginator,
                'page_obj': page,
                'is_paginated': is_paginated,
                'object_list': queryset
}
```
### tags
```

#tag
from django import template
from django.template.defaultfilters import stringfilter
from django.conf import settings

register = template.Library()

@register.simple_tag
@register.inclusion_tag('blog/tags/breadcrumb.html')

@register.filter(is_safe=True)
@stringfilter
  
```

## The model layer
```
#lib
from django.db import models
from django.core.urlresolvers import reverse

#auth
AUTH_USER_MODEL='auth.User'

```


## The template layer
```
#TEMPLATES
TEMPLATES 'DIRS': [os.path.join(BASE_DIR, 'templates')]

```

## The admin layer
```
from django.contrib import admin
admin.site.register(Article)

```


## ERRORS 
```
#error1
error:Add or change a related_name argument to the definition for 'BlogUser.groups' or 'User.groups'.
solution:AUTH_USER_MODEL='accounts.BlogUser'

#error2
error:django makemigrations no changes detected
solution:python manage.py makemigrations --empty yourappname 生成一个空的initial.py
```

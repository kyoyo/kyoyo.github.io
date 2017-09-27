---
layout: post
title: Django基础
category: 技术
tags: Django
keywords: 
description: 
---

###开发环境准备

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





### The view layer

```
#urls lib
from django.conf.urls import url,include

#views lib
from django.http import HttpResponse
from django.views import generic


#admin
from django.contrib import admin
admin.site.register(Article)



#setting
  #TEMPLATES
  TEMPLATES 'DIRS': [os.path.join(BASE_DIR, 'templates')]
  #auth
  AUTH_USER_MODEL='auth.User'

```


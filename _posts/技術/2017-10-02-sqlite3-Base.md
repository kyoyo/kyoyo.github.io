---
layout: post
title: sqlite3常用命令
category: 技术
tags: sqlite3
keywords: 
description: 
---

# 常用命令

```
#安装sqlite3


#创建数据库
sqlite3 testDB.db
 -注意: 进入sqlite3 之前执行此命令，如果数据库存在，直接作为main库使用

#数据库一览
.databases

#数据表一览
.tables

#数据库导出到sql文件
.output file.sql
.dump
.output stdout

#从sql文件导入到数据库
.read file.sql



```




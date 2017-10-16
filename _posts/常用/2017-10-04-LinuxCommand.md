---
layout: post
title: 常用命令
category: 常用
tags: commands
keywords: 
description: 
---

## Linux 常用命令
```
#环境变量表示
printenv

#查看用户和组
/etc/group

#系统存在的所有用户名
/etc/shadow

#系统存在的所有用户密码
/etc/passwd

#检索
find ./ -name 'strinfo'
egrep 'strinfo' filename.log

#检索指定文件含有指定字符串的行
grep -n "hello" test3
#检索含有指定字符串的文件，并搜索子目录
grep -rn "hello" * 
#指定多个字符串
grep -n 'hello \| you' * 

#检索文件
find ./ -name 'filename.log' -type f 

#cron
crontab -e

#更新内容自動表示
tail -f filename

#文件树结构
tree opt -L 2

#列出匹配的文件夹
ls -d log*

```




## sqlite3 常用命令
```
#安装sqlite3
请访问 SQLite 下载页面，从 Windows 区下载预编译的二进制文件。
您需要下载 sqlite-tools-win32-*.zip 和 sqlite-dll-win32-*.zip 压缩文件。
创建文件夹 C:\sqlite，并在此文件夹下解压上面两个压缩文件，将得到 sqlite3.def、sqlite3.dll 和 sqlite3.exe 文件。
添加 C:\sqlite 到 PATH 环境变量，最后在命令提示符下，使用 sqlite3 命令，将显示如下结果。

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

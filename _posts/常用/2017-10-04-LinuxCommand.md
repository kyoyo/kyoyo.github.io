---
layout: post
title: 常用命令
category: 常用
tags: commands
keywords: 
description: 
---

[好用的linux command 查询](http://man.linuxde.net/)

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

#查看shell种类
cat /etc/shells

#查看默认shell
echo $SHELL

#diff --exclude 不包括的路径设定   -r 遍历子目录 -q 只显示不同的文件
diff  --exclude='.tmp1' --exclude='.tmp2' -r -q  folder1 folder2

```
## umask
用来设定linux新规做成文件的权限赋予规则

```
#umask确认
$ umask
0002

#umask 权限确认
$ umask -S
u=rwx,g=rwx,o=rx

#umask 设定
$ umask 0022 

#umask计算方法
文件 666，文件夹 777 减去 想获得的权限就可以得到mask值 
例:
777-755=022
#指定权限来设定umask
umask u=rwx,g=rwx,o=rx
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

## ubuntu 设置

- root  账户
其实root账户是存在的，只是需要我们给它设置一个密码，然后使用的时候用root用户名登陆，然后输入对应的密码就就以root用户登录了，所以开启root账户，实际上就是给root用户设置一个密码的过程，下面我们就来给root设置密码，另外还需要注意的是，只能使安全ubuntu系统的时候创建的用户账号才能启用root账号，

使用下面的命令来给root账号设置密码：

sudo passwd root

- 

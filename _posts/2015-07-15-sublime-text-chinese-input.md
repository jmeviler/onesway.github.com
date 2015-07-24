---
layout: post
title: Ubuntu14.04 Sublime Text3 中文输入
categories: [tool,Sublime]
tags: [tool,Sublime]
description: Sublime Text3 Chinese Input whith sougo.
---

**1)**
    下载<a href="/img/sublime_text_chinese-input-method.tar.gz">压缩包</a>,此压缩包是在Ubuntu14.04下编译的.如其他版本请重新编译.

-----
**2)**
首先使用以下命令解压文件

    tar -xzvf sublime_text_chinese-input-method.tar.gz

然后可以看到三个文件

    1、libsublime-imfix.so
    2、sublime_imfix.c
    3、sublime_text.desktop

如果是Ubuntu14.04可以直接使用该文件,无需编译.

-----
**3)**
非Ubuntu14.04可以执行以下命令

    gcc -shared -o libsublime-imfix.so 目录/sublime_text_chinese-input-method/sublime_imfix.c  `pkg-config --libs --cflags gtk+-2.0` -fPIC

此命令需要用户直接编译文件共享库,确保安装有

    sudo apt-get install build-essential
    sudo apt-get install libgtk2.0-dev

-----
**4)**
将libsublime-imfix.so文件复制到Sublime的安装目录(一般是/opt/sublime_text/)

    sudo cp 目录/sublime_text_chinese-input-method/libsublime-imfix.so /opt/sublime_text/
    sudo cp 目录/sublime_text_chinese-input-method/sublime_text.desktop /opt/sublime_text/

-----
**5)**
修改启动项

    sudo subl /usr/bin/subl

修改/usr/bin/subl文件,将以下代码写入第一行

    export LD_PRELOAD=/opt/sublime_text/libsublime-imfix.so

保存后,在终端输入 subl 启动Sublime Text3试下.


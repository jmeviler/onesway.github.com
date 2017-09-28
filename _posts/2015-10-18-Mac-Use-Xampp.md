---
layout: post
title: Mac OS X 安装PHP继承环境Xampp
categories: [tools]
tags: [Xampp,php]
description: Install Xampp for OS X.
---

在OS X系统中`PHP`的集成开发环境最简单的事Xampp，Xampp集成了Apache+MySQL+PHP+PERL。<a href="https://www.apachefriends.org">官网</a>
**下载**
    可以选择 <a href="https://www.apachefriends.org/zh_cn/download.html">官网</a>的地址下载。
    速度快点开业从极客学院的资源 <a href="http://www.jikexueyuan.com/resources/">下载</a>。
**安装**
    将下载的dmg打开按照提示一步一步安装，此处不在赘述。
**启动**
    启动有两种方式，一是通过App启动，二是在终端下启动
    终端下启动使用以下命令：

    sudo /Applications/XAMPP/xamppfiles/xampp start

网上说这种方式可能会出现如下错误：

    XAMPP: Starting ProFTPD.../Applications/XAMPP/xamppfiles/xampp: line 184: /Applications/XAMPP/xamppfiles//var/proftpd/start.err: No such file or directory fail.
    Contents of "/Applications/XAMPP/xamppfiles//var/roftpd/start.err":
    cat: /Applications/XAMPP/xamppfiles//var/proftpd/start.err: No such file or directory

但是我在启动过程没有遇到。。

解决办法：

    sudo mkdir /Applications/XAMPP/xamppfiles/var/proftpd/
    touch /Applications/XAMPP/xamppfiles/var/proftpd/start.err
    sudo /Applications/XAMPP/xamppfiles/xampp fix_rights

安装成功之后，在浏览器输入`127.0.0.1`,出现黄色小界面就是证明安装成功～

Ps：这个时候你会发现在终端下输入

    mysql -uroot -p

会出现

    zsh: command not found: mysql

这是因为系统会在`/usr/bin`这个位置里寻找你输入的命令，如果你没有把命令引入到这个位置，无论你直接cd到工具具体的位置调用，是找不到的。
此时将`mysql`引入到`/usr/bin`下：

    ln -s /applications/xampp/bin/mysql /usr/bin

这个时候在输入`mysql -uroot -p`方可使用～

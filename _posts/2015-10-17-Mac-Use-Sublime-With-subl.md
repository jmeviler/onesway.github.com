---
layout: post
title: Mac 命令行下使用subl
categories: [Sublime]
tags: [Sublime]
description: Use Sublime Text3 with subl in Mac.
---

习惯了在Linux系统上使用Sublime Text这个编辑器，现在Mac上安装后，在命令行下运行subl竟然发现没有办法使用。
然后G了下，发现解决办法如下：

-1.
根据<a href="https://www.sublimetext.com/docs/3/osx_command_line.html">官方文档</a>解释是，
假如你的Sublime Text安装在`Applications`目录，并且你将 `~/bin` 目录放入`PATH`中，你可以运行`subl`命令。
此时根据官方文档上说明执行

    ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl

-2. 使用别名的方式

    alias subl='open -a "Sublime Text"'

以上两种方法可以在Mac的终端下使用subl来启动Sublime Text.

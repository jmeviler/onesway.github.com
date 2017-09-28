---
layout: post
title: Mac OS X 下配置Oh My Zsh
categories: [tools]
tags: [tools]
description: The setting of Oh My Zsh for OS X.
---

在以前介绍过Linux下安装Oh-My-Zsh的安装(<a href="http://blog.onesway.xyz/tools/2015/04/10/Oh-my-zsh.html">传送门</a>)。
因为在Linux系统下的`shell`喜欢使用`oh my zsh`，再 Mac 的配置相对于 Linux 下简单一点。
因为在Mac下已经预装了Zsh。

    $ cat /etc/shells

显示如下：

    /bin/bash
    /bin/csh
    /bin/ksh
    /bin/sh
    /bin/tcsh
    /bin/zsh

与Linux相比的话，同样的命令，Mac下会多出一个`/bin/zsh`，这就是Mac下预装好的zsh。

首先

    $chsh -s /bin/zsh

将当前的shell由bash改为zsh。（此处按照提示输入密码）

**安装oh-my-zsh**（<a href="http://ohmyz.sh">官网</a>）
1.自动安装

    wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh

2.手动安装

    git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
    cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc

此时推出当前的会话，重新打开一个终端，就可看到oh-my-zsh的彩色界面。

`oh-my-zsh`还提供有丰富非常丰富的<a href="https://github.com/robbyrussell/oh-my-zsh/wiki/Themes">主题</a>.
可以根据自己的习惯来配置。
`oh-my-zsh`的配置都在`.zshrc`中.
使用Sublime Text或其他的编辑器打开，将其配置复制进去。

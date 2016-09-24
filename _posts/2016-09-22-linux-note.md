---
layout: post
title: Install nvm and node.
categories: [node, note]
tags: [node, note]
description: note about install node in linux.
---


**生成SSH密钥过程**

* 查看是否已经有了ssh密钥：

    `cd ~/.ssh`
    如果没有密钥则不会有此文件夹，有则备份删除

* 生存密钥：

    `$ssh-keygen -t rsa -C "admin@onesway.xyz"`
    按3个回车，密码为空

* 在github上添加ssh密钥

    之前会得到两个文件`id_rsa`和`id_rsa.pub`
    这里添加的是“id_rsa.pub”里面的公钥

* 测试

    `ssh git@github.com`
    如果验证成功，出现以下提示

>PTY allocation request failed on channel 0
>Hi jmeviler! You've successfully authenticated, but GitHub does not provide shell access.
>Connection to github.com closed.

---
**安装nvm**

* git clone https://github.com/creationix/nvm.git ~/.nvm

* 然后打开 ~/.bashrc ,  ~/.profile , or  ~/.zshrc这三个文件，在其中添加：

`source ~/.nvm/nvm.sh`

* `nvm install v5.3.0`

---
**配置淘宝镜像**

* 打开.npmrc文件(在用户主目录下)加入以下配置信息：
    `registry = http://registry.npm.taobao.org`

* `npm config set registry "https://registry.npm.taobao.org"`

* 测试 查看 `npm config list`

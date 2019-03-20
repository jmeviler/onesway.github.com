---
layout: post
title: iTerm2 介绍及使用.
categories: [tools, Note]
tags: [tools, Note]
description: iTerm2 setting and use.
---

### iTerm2
 * 官网 [传送🚪](https://www.iterm2.com/)

### Install

  * [官网下载](https://www.iterm2.com/downloads.html), 下载后解压并安装

  * 使用 `Homebrew` 安装
    ```shell
      brew cask install iterm2
    ```

### Theme

  * `Preferences` -> `Profiles` -> `Colors` -> `Color Presets` 选择适合的主题

  * 也可以导入自己喜欢主题, 可以在[Iterm2-color-schemes](https://iterm2colorschemes.com/)挑选, 下载 `schemes` 下的 `itermcolors` 文件

  * 个人偏爱 [Solarized Dark Higher Contrast](https://github.com/mbadolato/iTerm2-Color-Schemes/blob/master/schemes/Solarized%20Dark%20Higher%20Contrast.itermcolors)

### Plugins

  * [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions), 需要配合 `Oh My Zsh`

    - 命令 `git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions` 克隆 `zsh-autosuggestions` 项目到指定目录

    - 打开iTerm2，编辑 `code ~/.zshrc` 文件，找到 `plugins` 配置

    - 在plugins配置中增加 `zsh-autosuggestions` 插件

    - 也可以按照官方教程, [Installation](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md)

### Proxy

  * 更新 `brew update` 异常缓慢, 可能需要用到代理, 下面需要配合小飞机使用

  * 可以在小飞机菜单中, 选择 `复制终端代理命令` 粘贴至 `iTerm2` 使用即可(只在当前tab下有效)

  * 在 `.zshrc` 中添加以下内容 (`端口`配置可能存在`差异`)

    ```js
      alias proxy='export all_proxy=socks5://127.0.0.1:1086'
      alias unproxy='unset all_proxy'
    ```

  * 在终端使用 `proxy` 使用代理 (只在当前tab下有效)

  * 在终端使用 `unproxy` 终止代理 (只在当前tab下有效)

  * 可以使用 `curl cip.cc` 命令, 查看当前代理



  Enjoy it!
---
layout: post
title: 前端常用的那些工具
categories: [tools, FE]
tags: [tools, FE]
description: 前端常用到那些 N 开头的工具.
---

### NVM

> NVM: Node Version Manager.

* 就是 `Node` 的版本管理工具, 让你在同一台机器上 `安装` 和 `切换` 不同版本 Node 的工具

* [官网](https://github.com/creationix/nvm)

* [Installation](https://github.com/creationix/nvm#installation)

* Upgrade

  - [Manual upgrade](https://github.com/creationix/nvm#manual-upgrade)

  - 依赖于 `zsh plugin` => [zsh-nvm](https://github.com/lukechilds/zsh-nvm#manually)


### NODE

> Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine.

* [官网](https://nodejs.org/zh-cn)

* Installation

  - `nvm install 8.0.0`
  - `nvm alias default 8.1.0`

* Upgrade 👆👆

  - 使用 `nvm` 进行 `Node` 的版本控制

### NPM

> npm(1) -- a JavaScript package manager

* `npm` 是 `JavaScript` 世界的包管理工具, 并且是 `Node.js` 平台的默认包管理工具。

* [官网](https://www.npmjs.cn/)

* Installation
  - 新版的 `nodejs` 已经集成了 `npm`, 所以在你安装 `node` 的时候, `npm` 也一并安装好了.

* Upgrade
  - [更新 npm](https://www.npmjs.cn/getting-started/installing-node/#2-%E6%9B%B4%E6%96%B0-npm)

  - 更新到最新版本  `npm install -g npm`

  - 更新到指定版本  `npm -g install npm@5.6.0` (`@` 后为 `指定版本号`)

### NRM

> NPM registry manager

* `nrm` can help you easy and fast switch between different npm registries,
now include: `npm, cnpm, taobao, nj(nodejitsu), rednpm`.

* [官网](https://github.com/Pana/nrm)

* Installation

  - `npm install -g nrm`


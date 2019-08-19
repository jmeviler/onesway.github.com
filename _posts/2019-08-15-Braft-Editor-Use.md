---
layout: post
title: Braft Editor 使用指北
categories: [Note]
tags: [Note]
description: How to user Braft Editor.
---

### 前言
  作为一只前端, 看到人家实现了牛逼的富文本交互, 再看看自己的实现, 总想做点什么.

### Introduction
  美观好用的React富文本编辑器, `antd` 社区精选组件, 基于draft-js开发的编辑器: [Braft Editor](https://braft.margox.cn/)

  - 完善的文本内容编辑功能
  - 诸多开放的编辑接口，良好的可扩展性
  - 允许插入图片、音视频等多媒体内容
  - 允许自定义多媒体内容的上传接口
  - 允许设置图片的左右浮动
  - 允许设置编辑器可用的颜色列表、字号以及字体
  - 允许自定义需要展示的控制按钮和展示顺序
  - 允许增加额外的自定义按钮
  - 多语言支持
  - 支持自定义扩展
  - [官方文档](https://www.yuque.com/braft-editor/be/lzwpnr)
  - [github仓库](https://github.com/margox/braft-editor)

### Installing
  ```bash
    # 使用npm安装
    npm install braft-editor --save
  ```

### Usage
  [[项目官网](https://braft.margox.cn/demos/basic)]提供了诸多场景下的使用范例，请前往查看。

### Notice
 - [编辑器作者特别提醒](https://www.yuque.com/braft-editor/be/lzwpnr#1bbbb204)
 - 使用 [表情包扩展模块](https://github.com/margox/braft-extensions#%E8%A1%A8%E6%83%85%E5%8C%85%E6%89%A9%E5%B1%95%E6%A8%A1%E5%9D%97) 时, 若使用了 `webpack的dll插件`, 需要将 `react`, `react-dom`, `react-dom/server` 三者加进 `dll名单` 中.
 - 自定义 `entity`, [官网demo](https://braft.margox.cn/demos/entity)

    - 在非选中文本添加实体时, 使用以下代码
    ```js
      const entity = { type: 'entity Name', mutability: 'IMMUTABLE', data: { value } }
      this.setState({
        editorState: ContentUtils.insertText(editorState, text, inlineStyle, entity), // 插入entity
      });
    ```
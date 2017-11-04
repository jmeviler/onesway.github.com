---
layout: post
title: VSCode's Settings
categories: [Note, tools]
tags: [Note, tools]
description: VSCode's Custom Settings.
---

* 近日我司更新机器, 死皮赖脸之下换了新机器, 趁机再把VSCode设置补充一下.

### 设置

* 打开 `首选项 -> 设置`, 弹出配置文件 `settings.json`.

```json
{
  "workbench.startupEditor": "newUntitledFile",
  // 控制字体系列。
  "editor.fontFamily": "Source Code Pro, Menlo, Monaco, 'Courier New', monospace",
  // 以像素为单位控制字号。
  "editor.fontSize": 14,
  // icon 主题定制
  "workbench.iconTheme": "vscode-icons",
  // 控制编辑器是否应呈现空白字符
  "editor.renderWhitespace": "all",
  // 启用后，将在保存文件时剪裁尾随空格。
  "files.trimTrailingWhitespace": true,
  // 一个制表符等于的空格数
  "editor.tabSize": 2,
  // 按 "Tab" 时插入空格。该设置在 `editor.detectIndentation` 启用时根据文件内容进行重写。
  "editor.insertSpaces": true,
  // 垂直标尺
  "editor.rulers": [120],
  "files.associations": {
    "*.vue": "vue"
  },
  "eslint.autoFixOnSave": true,
  "eslint.options": {
    "extensions": [
      ".js",
      ".vue"
    ]
  },
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "vue",
    "vue-html"
  ],
  "search.exclude": {
    "**/node_modules": true,
    "**/bower_components": true,
    "**/dist": true
},
  "emmet.syntaxProfiles": {
    "javascript": "jsx",
    "vue": "html",
    "vue-html": "html"
  },
  "extensions.autoUpdate": true,
  "editor.cursorBlinking": "smooth",
  "window.zoomLevel": 1
}

```
也可以点击<a href="/files/settings.json">此处</a>下载

### 键盘快捷方式

* 打开 `首选项 -> 键盘快捷方式`, 或者 `cmd+K cmd+S` 弹出配置文件 `keybindings.json`.

```json
[
  {  // 小写转大写
    "key": "cmd+k cmd+u",
    "command": "editor.action.transformToUppercase",
    "when": "editorTextFocus"
  },
  {  // 小写转大写
    "key": "cmd+k cmd+l",
    "command": "editor.action.transformToLowercase",
    "when": "editorTextFocus"
  },
  { // 查找下一个
    "key": "ctrl+g",
    "command": "editor.action.nextMatchFindAction",
    "when": "editorFocus"
  },
  {  // 查找行
    "key": "cmd+g",
    "command": "workbench.action.gotoLine"
  }
]
```

### 常用插件

[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

[Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame)

[Markdown PDF](https://marketplace.visualstudio.com/items?itemName=yzane.markdown-pdf)

[Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)

[Sass Lint](https://marketplace.visualstudio.com/items?itemName=glen-84.sass-lint)

[sort-imports](https://marketplace.visualstudio.com/items?itemName=amatiasq.sort-imports)

[stylelint](https://marketplace.visualstudio.com/items?itemName=shinnn.stylelint)

[vscode-icons](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)

[WakaTime](https://marketplace.visualstudio.com/items?itemName=WakaTime.vscode-wakatime)

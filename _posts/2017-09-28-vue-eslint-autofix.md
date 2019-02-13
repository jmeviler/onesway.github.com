---
layout: post
title: Vue中ESLint Autofix
categories: [tools, FE]
tags: [tools, FE]
description: autofix in .vue files
---

在使用 `vue-cli` 初始化项目后, 若启用 `eslint` 选项， 在项目中，只会告知何处出错, 并不会自动修复。手动去改, 费时费力。

1. 编译时Autofix

    安装 `eslint-plugin-vuefix` 插件

    ```bash
      npm i eslint-plugin-vuefix --save -g
    ```

    在 `.eslintrc.js` 添加

      ```json
        {
          "plugins": [
            "vuefix"
          ],
          "rules": {
            "vuefix/vuefix": [2, {"auto": true}]
          }
        }
      ```

    PS: 在 `plugins:[]` 这, 将 `vuefix` 放在前面或者不用 `html` 就可以autofix了, 但不可以放在html后面.

2. 命令行Autofix

    在 `vue-cli` 生成的项目中, `package.json` scripts中有 `"lint": "eslint --ext .js,.vue src"`

    在执行 `npm run lint` 时, 此命令只是检查eslint.
    若要自动修改, 修改为 `eslint --fix . --ext .js,.vue src`

3. 添加到pre-commit


    ```bash
      npm install --save-dev lint-staged husky
    ```

    更新 `package.json`

    ```json
      {
        "scripts": {
        "precommit": "lint-staged"
        },
        "lint-staged": {
          "*.{js,vue}": ["eslint --fix", "git add"]
        }
      }
    ```

4. VS Code 中 autofix

  > 在 VS Code 安装 [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)、 [vuetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)

  > 文件> 首选项 > 设置 > 用户设置 配置以下内容:

  ```json
  {
    "eslint.autoFixOnSave": true,
    "vetur.format.defaultFormatter.html": "js-beautify-html",
    "vetur.format.defaultFormatter.js": "vscode-typescript",
    "eslint.validate": [
      "javascript",
      {
        "language": "vue",
        "autoFix": true
      },
    ]
  }
  ```

  Enjoy it!
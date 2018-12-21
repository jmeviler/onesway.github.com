---
layout: post
title: Vue项目中添加scss-lint.
categories: [tools, FE]
tags: [tools, FE]
description: use scss-lint and pre-commit in vue project.
---

### Install stylelint 及相关

  ```bash
    npm i stylelint -D
    npm i stylelint-processor-html -D
    npm i stylelint-config-standard -D
  ```

### 配置stylelint

  在根目录下新建文件 `.stylelintrc` 并添加以下内容

  ```json
    {
      "processors": ["stylelint-processor-html"],
      "extends": "stylelint-config-standard",
      "rules": {
        // 自定义规则
      }
    }
  ```

### 添加 script

  在 `package.json` 添加以下内容

  ```json
    "scripts": {
      "lint:css": "stylelint '**/*.vue' --syntax scss"
    }
  ```

  此时终端运行 `npm run lint:css` 即可。

### 添加pre-commit

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
      "**/*.vue": ["stylelint --syntax scss", "git add"]
    }
  }
  ```

----

  PS:

  WIN7 如有提示： `lint-staged不是内部或外部命令，也不是可运行的程序。`

  请执行 `npm i pre-commit`, 后将`.git/hooks` 中的 `pre-commit.old` 内容复制到 `pre-commit`.

  WIN10 下若提示 `'**/*.vue' does not match any files`

  请按照以下方式修改
  ```json
  "scripts": {
    "lint:css": "stylelint **/*.vue"
  }
  ```

  相关文档：

  [husky](https://github.com/typicode/husky)

  [stylelint](https://github.com/stylelint/stylelint)

  [lint-staged](https://github.com/okonet/lint-staged)


  Enjoy it!
---
layout: post
title: Element UI 踩坑
categories: [Note, Javascript, UI]
tags: [Note, Javascript, UI]
description: Problems encountered in using Element UI development.
---

**el-form**

 * 表单提交

  1. Form内包含一个`input`时候，按`Enter`页面会刷新，并在url末尾添加一个`?`

  ```js
  <el-form label-width="80px" :model="form">
    <el-form-item label="名称">
      <el-input v-model="form.name"></el-input>
    </el-form-item>
  </el-form>
  ```

  解决方案： 在 `el-form` 上 添加 `@submit.prevent.native`

  [官方的解释](https://github.com/ElemeFE/element/issues/3625#issuecomment-310571719)是: 这是浏览器的默认行为，与 Element 和 Vue 都无关

----

  2. Form 内存在一个以上的 `input` 时，无法使用`Enter`提交表单

    ```js
    <el-form label-width="80px" :model="form">
      <el-form-item label="名称">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="类型">
        <el-input v-model="form.type"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button @click="onSubmit">Submit</el-button>
      </el-form-item>
    </el-form>
    ```

      解决方案： 设置 `el-button`的`native-type="submit"`

----

  3. Form 表单验证, `el-select` 中 `option` 绑定值为 `number` 时, 验证始终失败！[demo](http://jsbin.com/ciravejuye/edit?html,output)

----

  4. Form 表单验证, rules中type为 `number` 时， 只要开头为数字, 验证即可通过。。出错方式见[官方demo](https://jsfiddle.net/api/post/library/pure/)
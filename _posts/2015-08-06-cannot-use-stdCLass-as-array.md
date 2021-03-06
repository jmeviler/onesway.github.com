---
layout: post
title: Cannot use object of type stdClass as Array
categories: [PHP]
tags: [PHP]
description: Cannot use object of type stdClass as Array.
---

php在调用`json_decode`从字符串对象生成json对象时，如果使用`[]`操作符取数据，会得到下面的错误

**错误:**
`Cannot use object of type stdClass as array.`

**产生原因:**

    $res = json_decode($res);
    $res['key']; //把 json_decode() 后的对象当作数组使用。

**解决方法(2种):**

    1、使用 json_decode($data, true),就是使json_decode的第二个变量设置为 `true`。
    2、json_decode($res) 返回的是一个对象， 不可以使用 $res['key'] 进行访问，换成 $res->key 就可以了。

>参考手册：
>说明

> mixed json_decode ( string $json [, bool $assoc ] )
> 接受一个 JSON 格式的字符串并且把它转换为 PHP 变量

>参数

> json
> 待解码的 json string 格式的字符串。

> assoc
> 当该参数为 TRUE 时，将返回 array 而非 object 。

>返回值
> Returns an object or if the optional assoc parameter is TRUE, an associative array is instead returned.


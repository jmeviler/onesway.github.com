---
layout: post
title: Null和False,0,空字符串的关系
categories: [PHP]
tags: [PHP]
description: Null和False,0,空字符串的关系
---

    <?php
        //Null and 0
        echo 'Null and 0';
        echo var_dump(null==0);

        //Null and False
        echo 'Null and False';
        echo var_dump(null==false);

        //Null and 空字符串
        echo 'Null and 空字符串';
        echo var_dump(null=='');
    ?>

通过上面那段代码可以得到如下结果

    Null and 0: bool(true)
    Null and False: bool(true)
    Null and 空字符串: bool(true)

由此可见,PHP中的null,false,0和空字符串之间是可以相等的,这因为在PHP中它们都术语一种'非'类型,其他的'非'类型还包括空数组等.

----------

魔术方法:

    __construct():类构造函数
    __destruct():类的析构函数
    __get(string $name):当试图读取一个并不存在的的类属性时被调用
    __set(string $name,mixed $value) :给未定义的类变量赋值时被调用
    __call(string $name,array $arguments):当调用一个不可访问类方法时调用
    __callStatic(string $name,array $arguments):当调用一个不可访问的静态类方法时调用
    __toString():当打印一个类对象时被调用
    __clone():当类对象被克隆时调用
    __sleep():持久化一个类对象时,如果__sleep()方法存在则先被调用,然后才执行序列话操作.可用于清理对象
    __wakeup():与__sleep()相反,反持久化操作
    __isset():当对未定义的类变量调用isset()和empty()时,__isset会被调用
    __unset():unset()一个对象的属性时被调用
    __invoke():当尝试以调用一个函数的方式调用一个对象时,__invoke()方法会被自动调用
    __autoload):区别于以上所有方法,是一个全局方法

-------
JSON 是Javascript对象表示法(Javascript Object Notation)的简称,JSON协议源自Javascript脚本语言的对象的持久化表示方法.
在JSON协议中,最基本的数据结构有两种:
    1.数组结构["james","iris"]
    2.对象结构:{"id":1,"name":"james"}
    json_decode — 对 JSON 格式的字符串进行编码
    json_encode - 对变量进行JSON编码


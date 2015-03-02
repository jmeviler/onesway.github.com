---
layout: post
title: JS字符串截取和标签操作
categories: [Javascript]
tags: [Javascript]
description: JS字符串截取,获取某一元素下标签个数,删除指定的标签
---

JS字符串截取:
    var str = "abc_123";
    若截取字符串"123",则: str = str.substring(str.length-3,str.length);
    若截取字符串"abc",则: str = str.substring(0,str.length-4);

------
获取某一元素下标签个数:

    <div id='test'>
        <li>test001</li>
        <li>test002</li>
        <li>test003</li>
        <li>test004</li>
    </div>

JS Code:
    var count = document.getElementById("test").getElementByTagName("li").length;

-------
删除指定的标签:

    <div id='test'>
        <li>test001</li>
        <li>test002</li>
        <li>test003</li>
        <li>test004</li>
    </div>
    1.删除id为test标签(将li子标签一起删除):
    if(document.getElementById("test") != null){
        var obj = document.getElementById("test");
        obj.parentNode.removeChild(obj);
    }
    2.删除第一个li标签(仅删除第一个li):
    if(document.getElementById("test") != null){
        var count = document.getElementById("test").getElementsByTagName("li").length;
        var obj = document.getElementById("test");
        if(count > 1){
            var obj = document.getElementById("test");
            obj.removeChild(obj.childNodes[0]);
        }
    }
---
layout: post
title: Postman--API测试工具
categories: [tools]
tags: [tools]
description: Postman--API测试工具--Chrome
---

Postman 是一个功能强大的网页调试与发送网页HTTP请求的Chrome插件.<a href="http://www.getpostman.com/">官网传送门</a>

**安装(此处介绍离线版的):**

    1.打开Google Chrome 菜单->tools->Extensions
    2.勾选Developer mode(即打开开发者模式)->点击Load unpacked extension...
    3.找到下载好的文件夹,点击open.即可成功.(一定要选择Enabled).
    4.打开书签栏中的Apps,会看到一个名字为Postman-REST Client的插件.此时插件已安装成功.

------
**简介**

    1.模拟各种 HTTP requests:常用的GET、POST到RESTful的PUT 、DELETE...等等。
    2.Collection 功能:Collection 是 requests的集合，在做完一次测试的时，可以把此次的 request 存到特定的Collection里面,等到下次测试的时候,就不需要再次输入.
    3.返回结果:Postman返回结果的时候,会自动格式化,将JSON,XML,HTML整理成易阅读的格式,并且有颜色的区分.

------

------
离线包<a href="/files/Postman-REST-Client_v0.8.4.14.rar">下载</a>
PS:如果此版本不适合你，可以直接下载Postman的Google Chrome插件。将 `*.crx` 后缀改成`*.rar` 解压后即可，此处需要注意的是，将`_metadata` 修改成`metadata`。

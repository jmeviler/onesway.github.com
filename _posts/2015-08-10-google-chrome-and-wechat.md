---
layout: post
title: Google Chrome 模拟微信浏览器
categories: [tools]
tags: [tools]
description: Google Chrome 模拟微信浏览器.
---

在开发过程中或者想用电脑打开微信的页面的时候，大部分时候是需要模拟微信内置的浏览器。
-打开Google Chrome，按下F12.
-点击Toggle device mode(即小手机图标)
-在UA处填写以下

**微信安卓UA**

    mozilla/5.0 (linux; u; android 4.1.2; zh-cn; mi-one plus build/jzo54k) applewebkit/534.30 (khtml, like gecko) version/4.0 mobile safari/534.30 micromessenger/5.0.1.352

**微信iPhone UA**

    mozilla/5.0 (iphone; cpu iphone os 5_1_1 like mac os x) applewebkit/534.46 (khtml, like gecko) mobile/9b206 micromessenger/5.0

---
layout: post
title: 处理低版本IE记录(IE8, IE9)
categories: [Note, Javascript]
tags: [Note, Javascript]
description: Javascript Functions NOT supported by IE8, Placeholder not supported By IE9.
---

**stack overflow**

(1) indexOf() [see discussion & solution](http://stackoverflow.com/questions/1744310/how-to-fix-array-indexof-in-javascript-for-internet-explorer-browsers)

(2) base64() [See source](https://code.google.com/p/stringencoders/source/browse/trunk/javascript/base64.js?r=210)

(3) String.trim() [See discussion & solution](http://stackoverflow.com/questions/2308134/trim-in-javascript-not-working-in-ie)

(4) history.pushstate [See discussion & solution](http://stackoverflow.com/questions/6622449/emulate-polyfill-history-pushstate-in-ie)

(5) map() [See discussion & solution](https://stackoverflow.com/questions/7350912/is-the-javascript-map-function-supported-in-ie8)

(6) ArrayBuffer  (7) bind  (8) Create  (9) DataView  (10) every  (11) filter ...

**github**

* `ie8-js`: ie8 js fix for foundation framework and common ie8 css issues. [传送门](https://github.com/seeliang/ie8-js)

* `JavaScript polyfill`:  JavaScript Polyfills, Shims and More. [传送门](https://github.com/inexorabletash/polyfill)

**Placeholder**

* `jquery-html5-placeholder-shim`: HTML5 Placeholder support for non compliant browsers using jQuery. [传送门](https://github.com/parndt/jquery-html5-placeholder-shim)

>PS: 不支持国际化（可使用改变label的value实现）. 可能会出现错位，尝试修改`top: ot.top - op.top`.
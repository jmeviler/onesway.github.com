---
layout: post
title: Throttle and Debounce
categories: [Note]
tags: [Note]
description: You have to know this.
---

### Throttle
> 函数节流: 指定时间间隔内只会执行一次任务.

> 简而言之, 函数节流原理在规定的事件内, 只允许方法执行一次. 通过 `flag` 来判断当前函数是否执行完, 若执行完成, 则进行下一次的循环, 否则 `return` 掉.

* [demo](https://jsbin.com/pakapulane/embed?html,js,console,output)

<iframe src="https://jsbin.ably.io/unidir/1/edit" width="700px" height="500px" frameborder="0" scrolling="no"></iframe>

-----

### Debounce
> 函数防抖: 任务频繁触发的情况下, 只有任务触发的间隔超过指定间隔的时候, 任务才会执行.

> 其原理是通过闭包保存一个标记来保存 `setTimeout` 返回的值，每当用户触发相应的event时, 将前一个setTimeout `clear` 掉, 后又创建一个新的 `setTimeout`, 这样就能保证用户触发的事件是在 `interval` 间隔内.

```js
    function debounce(fn, interval = 300) {
        let timeout = null;
        return function () {
            clearTimeout(timeout);
            timeout = setTimeout(() => {
                fn.apply(this, arguments);
            }, interval);
        };
    }
```
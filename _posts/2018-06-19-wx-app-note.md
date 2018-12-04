---
layout: post
title: Mini Program Notes
categories: [Note]
tags: [Note]
description: mini program bugs and tips.
---

### Tips

 * 在 `Android` 机上, 调用 `wx.pageScrollTo` 时, 请将 `duration` 设置为 `0`

 * 安卓上, 当前页面全局可滚动时, 分享必须设置 `imgUrl`, 否则会滚动到顶部

 * 在使用微信自定义分析数据上报接口 `wx.reportAnalytics` 时, 避免在同一方法连续多次上报, 第二个可能会丢

 * 小程序内 退出 小程序 `navigator`

 * 跑马灯 `swiper` 在某些版本(`eg. v2.3.0+`) 配合开发者工具, 可使内存飙升

 * 开放能力 `open-data`, 样式变更 `display: block; overflow: hidden;`

 * `formId`, 最丧心病狂的[做法](https://developers.weixin.qq.com/community/develop/doc/0000e29a094a004fa7b75327c51c00)
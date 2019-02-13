---
layout: post
title: Mini Program Notes
categories: [Note, WxApp]
tags: [Note, WxApp]
description: mini program bugs and tips.
---

### Tips

 * 在 `Android` 机上, 调用 `wx.pageScrollTo` 时, 请将 `duration` 设置为 `0`

 * 安卓上, 当前页面全局可滚动时, 分享必须设置 `imgUrl`, 否则会滚动到顶部

 * 在使用微信自定义分析数据上报接口 `wx.reportAnalytics` 时, 避免在同一方法连续多次上报, 第二个可能会丢

 * 小程序内 退出 小程序. `navigator`

 * 跑马灯 `swiper` 在某些版本(`eg. v2.3.0+`) 配合开发者工具, 可使内存飙升

 * 开放能力 `open-data`, 样式变更 `display: block; overflow: hidden;`

 * 推送模版消息时, 配置路径的前不能带 `/`, 否则, 在 Android 上路径错误, iOS 上正常

 * `formId`, 最丧心病狂的[做法](https://developers.weixin.qq.com/community/develop/doc/0000e29a094a004fa7b75327c51c00)

 * 运用好 `WXS`, 据说 `iOS` 上比 `js` 快 2～20倍. [传送🚪](https://developers.weixin.qq.com/miniprogram/dev/framework/view/wxs/)

 * 不弹窗提示, 获取用户地理位置信息.

 * `云开发` 隐私敏感信息可配置在 `环境变量` 中, 使用 `process.env.xxx` 取值

 * 微信 `7.0` 起小程序内嵌 `web-view` 的 `UA` 带上了 `miniprogram` 的标识

 * 小程序跳转小程序 `(突破限制)`

    - 可以使用 `小程序码` (个人的赞赏码) 长按识别可跳转

    - 小程序内关联微信公众号文章, [文章内跳转小程序](https://developers.weixin.qq.com/community/develop/doc/000e86d76043a080e208a79ec51400)
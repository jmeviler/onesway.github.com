---
layout: post
title: Install Charles on Mac.
categories: [Note, Unix]
tags: [Note, Unix]
description: Install Charles on Mac.
---

>Charles is an HTTP proxy / HTTP monitor / Reverse Proxy that enables a developer to view all of the HTTP and SSL / HTTPS traffic between their machine and the Internet. This includes requests, responses and the HTTP headers (which contain the cookies and caching information).

## Install Charles

  ``` bash
    brew cask install charles
  ```

  Or

    官网下载(https://www.charlesproxy.com/download/),根据系统选择安装包。

## Config Charles

  ### 设置系统代理：

    >第一次启动 `Charles`, 会请求你给它设置系统代理的权限。输入登录密码授予 Charles 该权限。

    或者，

    >在需要将 `Charles` 设置成系统代理时，在 `Proxy -> Mac OS X Proxy` 来将 `Charles` 设置成系统代理.

  ### 抓取 iOS 上 `http/https` 请求

  在 Mac 电脑上安装证书

  ``` js
  "Help" -> "SSL Proxying" -> "Install Charles Root Certificate"
  ```

  > 系统默认是不信任 `Charles` 的证书的，此时对证书右键，在弹出的下拉菜单中选择 `显示简介`, 点击使用此证书时，把使用系统默认改为始终信任

  ![image](https://user-images.githubusercontent.com/8113957/27792604-234d2936-602d-11e7-826e-08c5b0f4fd97.png)

  在 iPhone 手机上安装证书

  ``` js
  "Help" -> "SSL Proxying" -> "Install Charles Root Certificate on a Mobile Device or Remote Browser"
  ```

  ![image](https://user-images.githubusercontent.com/8113957/27792236-5202dd54-602b-11e7-88ff-655a11c1fac4.png)


  在Safari中输入地址 `chls.pro/ssl`, 出现证书安装页面，点击安装手机设置有密码的输入密码进行安装

  > **PS:**<br>
    1) 手机上设置好 HTTP 代理<br/>
  2）Charles 需要开启

  ### Charles设置Proxy

  ``` js
  "Proxy" -> "SSL Proxying Settings..."
  ```

  勾选 `Enable SSL Proxying`, 点击 Add, `Host` 填写 `*`, `Port` 填写 `443`
  > `*` 代表统配


  即可抓取 iPhone `http/https` 请求

  > **PS**:
  > iOS 10.3(iOS11.2.6)下 Charles 抓包ssl证书信任问题
  > 设置->通用->关于本机->证书信任设置
  > 找到charles proxy custom root certificate然后信任该证书即可

---
layout: post
title: 安装 Jenkins
categories: [tools]
tags: [tools]
description: install Jenkins.
---

### 安装Jenkins

* Java 安装

  ```bash
    yum -y install java-1.8.0-openjdk-devel
  ```

* Jenkins 安装

  ```bash
    sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
    sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
    yum -y install jenkins
  ```

  >如果您以前从 Jenkins 导入过 key，那么 rpm --import 将失败，因为您已经有一个 key。

### 启动 Jenkins

  * 启动： 启动 Jenkins 并设置为开机启动：

  ```bash
    systemctl start jenkins.service
    chkconfig jenkins on
  ```

  > 此时Jinkens已经部署到你的 8080 端口

### 进入 Jenkins

  * 管理员密码

      登入 Jenkins 需要输入管理员密码，按照提示，我们使用以下命令查看初始密码：

      ```bash
        cat /var/lib/jenkins/secrets/initialAdminPassword
      ```

      复制密码，填入，进入 Jenkins。

  * 定制 Jenkins

    我们选择默认的 install suggested plugins 来安装插件。

  * 创建用户

    请填入相应信息创建用户，然后即可登入 Jenkins 的世界。
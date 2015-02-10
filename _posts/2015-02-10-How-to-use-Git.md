---
layout: post
title: How to use Git(1)
categories: [Git]
tags: [Git,Gitk,Git Flow]
description: How to use Git
---

1.What's Git?

    Git是目前世界上最先进的分布式版本控制系统.
        1.通俗的说,Git会保存你对文件的修改,并且能够对其他人的文件进行复制和整合. Git的保存叫做版本.
        2.Git的分布式:使得开发者不依赖于服务器,可以更加灵活的进行开发和分支管理.
    Git可以分为Working directory(工作区),Staging area(缓存区)和Repository(版本库)
    其中版本库又成为仓库,分为本地仓库和远程仓库.
    Working directory:
    当前Git仓库所在的目录即可理解为工作区,一切的增,删,改等操作均发生在工作区.
    Staging area:
    类似于虚拟的工作区,在.git目录下的index文件,记录了文件名,状态等.
    Repository:
    最显著的特点就是鼓励每个改动都先创建一个分支，完成改动后再把分支合并回主分支里面.
    在Git中任何一个文件都有三种状态,即:已提交的(committed);已修改的(modified);已暂存的(staged).
    三者之间的转换可以参考下图:
    
    <img src="/img/git.png" width="400" height="300">


2.Git's Branches
    git的分支可以分为主分支和辅助性分支.
    1.主分支主要有:master 和 develop构成.master分支可以理解为当前项目生产环境的分支.
    develop分支是主开发分支,是与master分支并行的一个分支.develop分支的源码到达了一个稳定状态待发布，所有的代码变更需要以某种方式合并到master分支，然后标记一个版本号.
    2.辅助性分支有Feature branches,Release branches和Hotfix branches .详情参考<a href="http://nvie.com/posts/a-successful-git-branching-model/" target="_blank">A successful Git branching model</a>
    Feature branches:
        可能从develop分支分离而来,但是必须合并到develop分支.主要是:为即将发布或者未来发布版开发新的功能.
    Release branches:
        可能从develop分支分离而来，但是一定要合并到develop和master分支上主要是:为新产品的发布做准备的.
    Hotfix branches:
        可以基于master分支，必须合并回develop和master分支。其功能与release分支相似,但是是未经计划的,如突然出现的BUG.
        (需要注意的是:如果一个release分支已经存在，那么应该把hotfix合并到这个release分支，而不是合并到develop分支).
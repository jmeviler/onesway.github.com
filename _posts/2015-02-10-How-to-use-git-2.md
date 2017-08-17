---
layout: post
title: How to use Git(2)
categories: [Git]
tags: [Git,Gitk,Git Flow]
description: How to use Git
---

###How to use Git?


1.**基本配置:**
        generate ssh
        >>$ssh-keygen
        clone project
        >>$git clone git@git.augmentum.com.cn:ibuzhai/ihiking-web.git
        set user name
        >>$git config --global user.name 'Your Name'
        set user email
        >>$git config --global user.emai'YourName@augmentum.com.cn'

2.**初始化**
在配置好git后,可以有两种初始化方式
        1.To commit local files
        >>$git init
        >>$git add .
        >>$git commit -m "initial commit"
        2.To clone content that's already on the site
        >>$git clone https://onesway@gitdemo.scm.chinacloudsites.cn:443/gitdemo.git
        >>建立远程代码库
        >>$git remote add origin https://onesway@gitdemo.scm.chinacloudsites.cn:443/gitdemo.git
        >>$git push origin master
此时初始化完成

3.**基本使用:**

    --create branch
        $git branch your_branch_name
        $git checkout -b your_branch_name

    --delete branch
        $git branch -D(d) your_branch_name

    --check repository status
        $git status
    --add modified/untracked file[s]
        $git add -A
        $git add file[s] name

    --commit changes
        $git commit -m "comment..."
    --push new cogit push origin
        $git push origin your_origin_name

4.**常用命令:**
在Git中获取帮助,可以使用man git-***的格式.

    $git-add : Add file contents to the index.
    $git-branch : List, create, or delete branches.
    $git-checkout: Checkout a branch or paths to the working tree.
    $git-cherry-pick: Apply the changes introduced by some existing commits.
    $git-commit: Record changes to the repository.
    $git-clone: Clone a repository into a new directory.
    $git-diff: Show changes between commits, commit and working tree, etc.
    $git-fetch: Download objects and refs from another repository.
    $git-init: Create an empty Git repository or reinitialize an existing one.
    $git-log : Show commit logs.
    $git-merge: Join two or more development histories together.
    $git-pull: Fetch from and integrate with another repository or a local branch.
    $git-push: Update remote refs along with associated objects.
    $git-rebase: Forward-port local commits to the updated upstream head.
    $git-reset: Reset current HEAD to the specified state.
    $git-stash: Stash the changes in a dirty working directory away.
    $git-status: Show the working tree status.



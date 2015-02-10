---
layout: post
title: How to use Git(2)
categories: [Git]
tags: [Git,Gitk,Git Flow]
description: How to use Git
---

###How to use Git?


1.**基本配置:**
>generate ssh  
>>$ssh-keygen  
>clone project   
>>$git clone git@git.augmentum.com.cn:ibuzhai/ihiking-web.git  
>set user name   
>>$git config --global user.name 'Your Name'   
>set user email  
>>$git config --global user.emai'YourName@augmentum.com.cn'    
2.**初始化**  
在配置好git后,可以有两种初始化方式  
>1.To commit local files  
>>git init  
>>git add .  
>>git commit -m "initial commit"                      
>2.To clone content that's already on the site  
>>git clone https://onesway@gitdemo.scm.chinacloudsites.cn:443/gitdemo.git  
>>建立远程代码库   
>>git remote add origin https://onesway@gitdemo.scm.chinacloudsites.cn:443/gitdemo.git  
>>git push origin master    
此时初始化完成  
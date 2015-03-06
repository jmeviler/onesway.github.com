---
layout: post
title: Sublime Text3 User Setting
categories: [Sublime]
tags: [Sublime]
description: Sublime Text3 User Setting
---

简单常用的Sublime Text的配置

    {
        "draw_white_space": "all",//空格一直显示
        "ensure_newline_at_eof_on_save": true,//保存文件时光标会在文件的最后向下换一行
        "file_exclude_patterns"://哪些文件会被显示到边栏上(用户自定义)
        [
            "node_modules"
        ],
        "highlight_modified_tabs": true,//高亮未保存文件
        "ignored_packages":// 删除你想要忽略的插件，需要重启
        [
            "Vintage"
        ],
        "rulers"://列显示垂直标尺，在中括号里填入数字，宽度按字符计算
        [
            119
        ],
        "tab_size": 4,// Tab键制表符宽度
        "translate_tabs_to_spaces": true,//缩进和遇到Tab键时使用空格替代
        "trim_trailing_white_space_on_save": true //保存文件时会删除每行结束后多余的空格
    }


常用快捷键
    Ctrl+D 选词
    Ctrl+P 查找当前项目中的文件和快速搜索
    Ctrl+R 快速列出/跳转到某个函数(当前文件)
    Ctrl+F 当前文件搜索
    Ctrl+Shift+F 当前项目搜索(替换)
    Ctrl+K+U 改为大写
    Ctrl+K+L 改为小写
    Ctrl+K+B 开启/关闭侧边栏
    Ctrl+Shift+/ 注释已选择内容
    Ctrl+/ 注释当前行
    Ctrl+Shift+↑可以移动此行代码，与上行互换
    Ctrl+Shift+↓可以移动此行代码，与下行互换

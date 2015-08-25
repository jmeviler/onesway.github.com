---
layout: post
title: PHP中二维数组排序的实现
categories: [PHP]
tags: [PHP]
description: PHP中二维数组排序的实现.
---

php中一维数组排序可以使用`asort`、`ksort`等一些方法进程排序，相对来说比较简单。二维数组的排序怎么实现呢？使用`array_multisort`和`usort`可以实现。

例如以下二维数组

    $users = array(
        array('name' => 'bowen', 'age' => 20),
        array('name' => 'jack', 'age' => 18),
        array('name' => 'ben', 'age' => 22)
    );

现在希望通过age进行排序。有以下两种方案：

-1、使用`array_multisort`

    $ages = array();
    foreach ($users as $user) {
        $ages[] = $user['age'];
    }
    array_multisort($ages, SORT_DESC, $users);

>将age提取出来存到一维数组`$ages`中，而后按照`age`降序排列。

同理可以先对年龄降序排列，再对姓名升序排列。

    $ages = array();
    foreach ($users as $user) {
        $ages[] = $user['age'];
    }
    $names = array();
    foreach ($users as $user) {
        $names[] = $user['name'];
    }
    array_multisort($ages, SORT_DESC, $names, SORT_ASC, $users);

-2、使用`usort`

    usort($users, function($a, $b) {
        $al = strlen($a['name']);
        $bl = strlen($b['name']);
        if ($al == $bl)
            return 0;
        return ($al > $bl) ? -1 : 1;
    });

>这里使用了匿名函数，如果有需要也可以单独提取出来。其中$a,$b可以理解为$users数组下的元素，可以直接索引name值，并计算长度，而后比较长度就可以了。

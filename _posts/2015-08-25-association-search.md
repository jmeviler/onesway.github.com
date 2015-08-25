---
layout: post
title: JS 与 PHP 实现联想查询
categories: [PHP]
tags: [PHP]
description: association search with javascript and php.
---

>今天在项目中需要实现一个自动提示的搜索功能(联想查询)。起初并不知道怎么实现的。后来Google、度娘了下。其大致思路是根据用户的输入，通过JQuery实时查询数据库，将其以列表的形式展现出来。

html代码如下：

    <form>
        <input type="text" size="30" value="" id="search" onkeyup="lookup(this.value);" onblur="fill();" />
        <div class="associationBox" id="association" style="display: none;">
            <div class="association" id="associationsList">
            </div>
        </div>
    </form>

>上述代码很容易理解， `input`用于接收用户输入信息。两个`div`用于显示联想查询的结果。

JS代码：

    <script type="text/javascript">
        function lookup(search) {
            if(trim(search.length) == 0) {
                $('#association').hide();
            } else {
                $.post("search.php", {queryString: ""+search+""}, function(data){
                    if(data.length >0) {
                        $('#association').show();
                        $('#associationsList').html(data);
                    }
                });
            }
        }
        function fill(thisValue) {
            $('#search').val(thisValue);
            setTimeout("$('#association').hide();", 200);
        }
    </script>

>`trim(search.length) == 0` 用于判断用户输入是否为空。

    $.post("search.php", {queryString: ""+search+""}, function(data){
        if(data.length >0) {
            $('#association').show();
            $('#associationsList').html(data);
        }
    });

>`post`请求，将`search`的内容以post的方式发送到`search.php`这个页面中，如果返回的数据不为`null`的话，将数据写入到页面(即上面html两个`div`中)。

PHP代码(此处只显示部分代码)：

    $query = $db->query("SELECT field FROM table WHERE search_field LIKE '$search%' LIMIT 10");
    if($query) {
        while ($result = $query ->fetch_object()) {
            echo '<li onClick="fill(\''.$result->value.'\');">'.$result->value.'</li>';
        }
    } else {
        echo '暂无数据.';
    }

>链接数据库后，根据html页传输过的search内容进行查询。将其循环输出。而后通过js将其写在html页面上。
>进而实现了联想搜索。


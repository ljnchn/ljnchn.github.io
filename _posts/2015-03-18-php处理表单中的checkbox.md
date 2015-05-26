---
layout: post
tags: php
title: php处理表单中的checkbox
---

最近做form表单提交的时候，复选框checkbox提交的数据不知道怎么处理，后来查了些资料后发现，关键点在于checkbox的name属性上。需要给checkbox一个统一的数组形式的name，例如mycheckbox[]。然后将数据传给一个数组中，循环输出就可以了。下面是一个简单的例子。
####form表单代码：
```html
<input name="hobby[]" type="checkbox" value="篮球" />篮球
<input name="hobby[]" type="checkbox" value="足球" />足球
```
####PHP代码
```php
<?php 
    var_dump($_POST);
    if (isset($_POST["hobby"])) {
        foreach ($_POST["hobby"] as $hobby) {
            echo "爱好是：{$hobby}<br />";
        }
    }
?>
```
---
date: 2016-09-23
layout: post
published: true
title:  Yii2 的多语言切换设置
tags:
- Yii2
---

# Yii2 的多语言切换设置

> Yii2 的多语言设置。我是通过判断 cookie 实现的，每次加载页面前，根据 cookie 设置语言
> 如果有 BaseController 的话，在里面的 init 方法写相关的逻辑最好。
> 如果没有，只能在配置文件的 on beforeAction 写了。

### 切换语言的方法，GET 方式接收需要切换的语言

``` php
public function actionLanguage()
{
    $lang = \Yii::$app->request->get('lang');  
    if(isset($lang)){  
        $cookie = new \yii\web\Cookie([
                   'name' => 'lang',
                   'expire' => time() + 36000000,
                   'httpOnly' => true,
                   'value' => $lang,
        ]);
        \Yii::$app->response->getCookies()->add($cookie);
    }
    //切换完语言哪来的返回到哪里
    $this->goBack(\Yii::$app->request->headers['Referer']);  
}
```

### 页面加载前，根据 cookie 设置语言

``` php
$config = [
    'on beforeAction' => function($event) {
        $cookie = \Yii::$app->request->cookies;
        if ($lang = $cookie->get('lang')) {
            \Yii::$app->language = $lang;
        }
    }
];
```

---
layout: post
tags: javascript
title: 关于javascript通过ID直接获取节点对象方法的一些思考
---

学习javascript（以下简称JS）的时候，通过ID获取节点对象的方法，书上以及手册都是这样写的：
```js
var idnode=document.GetElementById("idname")
```
然后再用获取到idnode更改样式，比如：
```js
idnode.style.color="#ff0"
```
但是偶然的机会看到有人是这样写的：
```js
idname.style.color
```
我的第一感觉是这样写肯定出错。但是这样的写法竟然可以获得和第一种方法同样的结果！太不科学了，如果可以这么简单的获取节点对象，那么第一种方法不是可以淘汰了吗？然后查了一些资料，第二种方法只是在一些高版本的浏览器可以使用，兼容性很差。而且不是很符合JS的语法规范。如果是自己简单的做个demo之类的，可以用用。正规开发还是使用第一种方法吧。
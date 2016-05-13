---
date: 2016-05-13 14:00
layout: post
status: public
title: Vue.js 的简单介绍
---

###  Vue.js 是什么？
`Vue.js`（读音 /vjuː/, 类似于 view）是一个构建数据驱动的 web 界面的库。`Vue.js `通过简单的 API 实现了响应的数据绑定和组合的视图组件。
简单来说，Vue.js 就是一个`MVVM`架构的前端框架。

###  Vue.js 有哪些特点
![vue的特点](/public/imgs/160513/vue.png)

-  响应的数据绑定
 Vue.js 的核心是一个响应的数据绑定系统，它让数据与 DOM 保持同步非常简单。在使用 jQuery 手工操作 DOM 时，我们的代码常常是命令式的、重复的与易错的。Vue.js 拥抱数据驱动的视图概念。通俗地讲，它意味着我们在普通 HTML 模板中使用特殊的语法将 DOM “绑定”到底层数据。一旦创建了绑定，DOM 将与数据保持同步。每当修改了数据，DOM 便相应地更新。这样我们应用中的逻辑就几乎都是直接修改数据了，不必与 DOM 更新搅在一起。这让我们的代码更容易撰写、理解与维护。![MVVM](/public/imgs/160513/mvvm.png)
- 组件系统
组件系统是 Vue.js 另一个重要概念，因为它提供了一种抽象，让我们可以用独立可复用的小组件来构建大型应用。如果我们考虑到这点，几乎任意类型的应用的界面都可以抽象为一个组件树：
![components](/public/imgs/160513/components.png)

###  简单例子
``` html
<!-- 这是我们的 View -->
<div id="example-1">
  Hello {{ name }}!
</div>

```

``` javascript
// 这是我们的 Model
var exampleData = {
  name: 'Vue.js'
}
// 创建一个 Vue 实例或 "ViewModel"
// 它连接 View 与 Model
var exampleVM = new Vue({
  el: '#example-1',
  data: exampleData
})
```
显示结果
> Hello Vue.js 

[基础实例](http://cn.vuejs.org/guide/)
[表单实例](http://cn.vuejs.org/guide/forms.html#Radio)

###  结合业务
![unpaid](/public/imgs/160513/unpaid.png)






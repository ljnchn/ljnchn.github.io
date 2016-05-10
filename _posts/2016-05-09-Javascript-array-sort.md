---
layout: post
title: Javascript 中数组元素的排序及洗牌算法的实现
---

> 这里利用了一个 sort 函数进行排序

### 正向排序

``` javascript
var numberArray = [2,1,3];
numberArray.sort(function(a, b){
        return a-b;
    }
); 
//[1,2,3]
```

### 逆向排序

```
var numberArray = [2,1,3];
numberArray.sort(function(a, b){
        return b-a;
    }
); 
//[3,2,1]
```

### 随机排序（洗牌）

```
var numberArray = [2,1,3];
numberArray.sort(function(){
        return Math.random()-0.5;
    }
); 
//random
```

> 可以看到，排序的是由匿名函数的返回值决定。 false 是正序， true 是逆序，0为不排序，随机则是随机结果。

参考链接[MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)

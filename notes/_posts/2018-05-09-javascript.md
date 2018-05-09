---
layout: post
category: note
title: javascript
subtitle: javascript es6 properties
excerpt: A brief introduction of javascript es6 properties.
time: 2018.05.09 11:44:37
tags:
- JavaScript
---
#### ES6的新特性
1.let的使用需要"严格声明",即在页面需要加上`'use strict'`的标识.  
2.ES6新增let和const两个变量声明命令，他们都具有如下特性：  
>1、块局作用域；  
2、不存在变量提升，一定声明后才能使用；  
3、暂时性死区，在代码块内使用let命令声明变量之前，该变量都是不可用的，不受外部变量影响；  
4、在相同作用域范围内不允许重复声明；  

`const`与`let`不同点在于：
>1、const如果声明的变量是简单的值，则不能改变变量的值，修改会报错；  
2、const如果声明的是复合类型的变量，则只保证变量地址不变，值可以变；

``` javascript 
    function hehda(){
        //测试代码块
    }
```
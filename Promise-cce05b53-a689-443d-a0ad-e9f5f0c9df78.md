# Promise

Class: JavaScript
Created: Sep 23, 2019 9:50 PM
Reviewed: Yes

# 什么是Promise？

Promise对象用于表示一个异步操作的最终完成（或失败），及其结果值。

Promise 对象是一个代理对象（代理一个值），被代理的值在Promise对象创建时可能是未知的。它允许你为异步操作的成功和失败分别绑定相应的处理方法（handlers）。 

这让异步方法可以像同步方法那样返回值，但并不是立即返回最终执行结果，而是一个能代表未来出现的结果的promise对象。

一个Promise的状态：

- pending 初始状态
- fullfilled 操作成功完成
- rejected 操作失败

## 语法

    new Promise( function(resolve, reject) {...} /*executor*/ );

### executor

executor是带有 resolve 和 reject 两个参数的函数 。（executor 函数在Promise构造函数返回所建promise实例对象前被调用）resolve 和 reject 函数被调用时，分别将promise的状态改为fulfilled（完成）或rejected（失败）。

## 属性

- Promise.resolve ( value )

返回一个状态由给定value决定的Promise对象。

[Promise](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise)

MDN | Promise讲解
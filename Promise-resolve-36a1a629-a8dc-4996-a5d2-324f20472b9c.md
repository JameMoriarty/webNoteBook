# Promise.resolve( )

Dtae: Sep 23, 2019
Reviewed: No
Status: JavaScript
频率: ⭐

Promise.resolve ( value )方法返回一个给定值解析后的Promise对象。如果该值为promise，则返回这个promise；如果这个值数thenable（即带有“then”方法），返回的promise会跟随这个thenable的对象，采用他的最终状态；否则返回的promise将以此值完成。

此函数将类promise对象的多层嵌套展平。

不要在解析为自身的thenable 上调用Promise.resolve。这将导致无限递归，因为它试图展平无限嵌套的promise。一个例子是将它与Angular中的异步管道一起使用。

### 语法

    Promise.resolve(value);

参数value是将被Promise对象解析的参数。

返回值是一个解析过带着指定值的Promise对象。

[Promise.resolve()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise/resolve)
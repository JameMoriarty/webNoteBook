# filter方法

Reviewed: No
Status: JavaScript
频率: ⭐⭐⭐

filter() 方法创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。

    var newArray = arr.filter(callback(element[, index[, array]])[, thisArg])

**参数：**

**`callback`**

用来测试数组的每个元素的函数。返回 `true` 表示该元素通过测试，保留该元素，`false` 则不保留。它接受以下三个参数：

**`element`**

数组中当前正在处理的元素。

**`index`可选**

正在处理的元素在数组中的索引。

**`array`可选**

调用了 `filter` 的数组本身。

**`thisArg`可选**

执行 `callback` 时，用于 `this` 的值。

[Array.prototype.filter()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
# const

Created: Sep 28, 2019 10:20 PM
Reviewed: No

const是常量，是用于块级作用域中，它的值不能通过重新赋值来改变。

与var变量不同，全局常量不会变为窗口对象的属性。需要一个常数的初始化器；也就是说，您必须在声明的同一语句中指定它的值（这是有道理的，因为以后不能更改）。

const声明创建一个值的只读引用。但这并不意味着它所持有的值是不可变的，只是变量标识符不能重新分配。例如，在引用内容是对象的情况下，这意味着可以改变对象的内容（例如，其参数）。

一个常量不能和它所在作用域内的其他变量或函数拥有相同的名称。

关于“暂存死区”的所有讨论都适用于let和const。

[const](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const)
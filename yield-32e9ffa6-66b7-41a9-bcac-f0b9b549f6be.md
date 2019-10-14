# yield*

优先级: 2
关联性: 从右到左
运算符: yield* ...

yield* 表达式用于委托给另一个generator 或可迭代对象。

    function* g1() {
      yield 2;
      yield 3;
      yield 4;
    }
    
    function* g2() {
      yield 1;
      yield* g1(); //委托给了g1()，进入g1()函数，在g1()函数结束之后回到这个函数
      yield 5;
    }
    
    var iterator = g2();
    
    console.log(iterator.next()); // { value: 1, done: false }
    console.log(iterator.next()); // { value: 2, done: false }
    console.log(iterator.next()); // { value: 3, done: false }
    console.log(iterator.next()); // { value: 4, done: false }
    console.log(iterator.next()); // { value: 5, done: false }
    console.log(iterator.next()); // { value: undefined, done: true }

[yield*](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/yield*)
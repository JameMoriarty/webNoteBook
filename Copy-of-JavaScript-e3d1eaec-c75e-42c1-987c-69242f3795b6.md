# Copy of JavaScript堆和栈（内存管理）

Reviewed: No
Status: 基础
频率: ⭐

# javascript内存管理（堆和栈）

## 堆（heap）

heap是没有结构的，杂乱无章的。一般用于给复杂数据类型（引用数据类型） 分配空间。

引用数据类型：Object、Array、Date、Function、RegExp、基本包装类型（Boolean、Number、String）、单体内置对象（Global对象、Math对象）

程序运行时每一个进程分配一个heap，heap的大小不确定，需要的话是可以增加的。

## 栈（stack）

stack是有结构的，每个区块要按照一定的次序（后进先出），存放一些基本类型的变量和对象的引用。存在stack中的数据的大小和生存期必须是确定的。

stack的寻址速度快于heap

程序运行时每一个线程分配一个stack，stack是线程独占的，heap是线程共享的。

当stack创建的时候，大小是确定的，如果数据超过satck的大小就会发生溢出错误（stack overflow）。
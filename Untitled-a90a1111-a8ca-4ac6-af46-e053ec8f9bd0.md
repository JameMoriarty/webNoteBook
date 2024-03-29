# 进程与线程

Class: 操作系统
Created: Sep 21, 2019 10:30 PM
Materials: http://blog.sina.com.cn/s/blog_5a2bbc860101gedc.html
Reviewed: Yes

# 背景

操作系统为了实现并行执行多任务而产生的概念。

# 进程

对操作系统来说一个任务就是一个进程（process），即可并发执行的程序在某个数据集合撒谎给你的一次计算活动。

是操作系统进行资源分配和调度的基本单位。

## 进程与程序的联系与区别

1. 程序是指令的有序集合，是一个静态的概念。进程是程序在处理机上的一次执行过程，是一个动态的概念。
2. 程序可以作为计算机资料长期使用，进程是有生命周期的。
3. 进程是由程序、数据、进程控制块三部分组成的。
4. 通过多次执行，一个程序可以对应多个进程；通过调用关系，一个进程可以包括多个程序。

## 进程的特征

1. 动态性
2. 并发性
3. 独立性
4. 制约性

## 进程的三种基本状态

1. 运行态
2. 就绪状态
3. 等待态（阻塞态）

# 线程

为了减少程序并行执行时所付出的时空开销，是的并发粒度更细、并发性更好。

是操作系统进程中能够并发执行的实体，是处理器调度和分派的基本单位。

## 为什么要引入线程？

创建一个新线程花费的时间少，两个线程的切换花费的时间少，同意进程内的线程共享文件和内存，他们之间互相通信不需要调用内核。

# 线程和进程的区别

1. 进程是资源分配的最小单位，线程是程序执行的最小单位。
2. 进程有自己独立的地址空间，线程共享进程中的数据，使用相同的地址空间，创建一个线程的开销要比进程小很多。
3. 线程之间的通信更加方便，同意进程下的线程共享全局变量、静态变量等数据，而进程之间通信需要以通信的方式（IPC）进行。
4. 多进程程序更健壮，因为进程之间不会互相影响；多线程程序只要有一个线程死掉，整个进程就死掉了。
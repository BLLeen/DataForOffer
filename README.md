# DataForOffer

主要记录2020年一月份以来面试所遇到的问题

## :pencil2: 算法

### 删除排序数组中的重复项
力扣原题：[https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)

### 反转链表

力扣原题：[https://leetcode-cn.com/problems/reverse-linked-list/](https://leetcode-cn.com/problems/reverse-linked-list/)

### 如何设计三台电梯的算法

说思路，尽可能多的把情况都想到，考察的是解决问题的能力。可以先从一台电梯的算法开始设计。

### 简述快排要求如何推断时间复杂度


### 如何创建一个队列，优先队列，最大（小）堆


### 什么是哈希表，冲突如何解决？


## :computer: 操作系统

### 进程、线程、协程的区别

### Linux常用信号（SIG）

### 存储卷的概念？

### 软连接、硬链接分别是什么？

### select和epoll的区别

## :cloud: 网络 

### 数据链路层如何保证可靠性传输

### TCP和UDP差别

### TCP如何保证可靠性

### TCP三次握手，四次挥手？为什么有等待时间？

### RST报文的作用？

### 哪个命令可以看到TCP的状态？

### 大量TCP链接处在TIME_WAIT2状态，可能地原因是啥？怎么处理？

### HTTP1.0、1.1、2.0的差别，以及HTTPS的差别

### HTTP多路复用是什么？

### HTTP状态码

### Cookies和Session的区别



## :floppy_disk: 数据库

### 数据库引擎有哪些？区别是啥？

### Innodb的默认索引是哪种数据结构？为什么使用这个结构？

### 有些数据库索引使用B树而有些使用B+树，为什么？

### 什么是回表查询？如何避免？

### SQL注入是啥？怎么避免？

## :fire: Golang

### 基础试题

Go面试题答案与解析[https://yushuangqi.com/blog/2017/golang-mian-shi-ti-da-an-yujie-xi.html](https://yushuangqi.com/blog/2017/golang-mian-shi-ti-da-an-yujie-xi.html)

### 数组和切片的区别

### 切片如何扩容的？

### Channel的作用？能传送什么数据？

### Context的作用？有哪几个方法（函数）？

### 如何实现一把锁？

### go map怎么实现的，协程安全的吗？为什么？

### go协程是如何调度的？

### go的GC如何工作的？

### 如何处理内存泄漏？

### go并发编程实现：一个查询功能，要求1.有1000并发数限制 2.有一个协程查到结果立马返回结束 3.每个线程都有超时时间10s

## :sparkles: Redis

### 如何设计发送短信验证码，要求1分钟内只能发1次，5分钟内最多能发2次，10分钟内最多能发3次？


### :truck: Docker & K8s

### pod是如何做到优雅的退出的?

### k8s有哪些组件？分别干什么用的？

### kubectl logs的流程？
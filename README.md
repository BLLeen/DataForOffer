# DataForOffer

主要记录2020年一月份以来面试所遇到的问题

## :pencil2: 算法

### 删除排序数组中的重复项
力扣原题：[https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)

### 反转链表

力扣原题：[https://leetcode-cn.com/problems/reverse-linked-list/](https://leetcode-cn.com/problems/reverse-linked-list/)

### 如何设计三台电梯的算法？

说思路，尽可能多的把情况都想到，考察的是解决问题的能力。可以先从一台电梯的算法开始设计。

### 简述快排，如何推导时间复杂度？

主要思想：以数组第一个数为基准mid，从数组的起始位置为i，末尾为j，比较mid和位置为i的大小，如果位置为i的值小于mid，则这两个交换位置并且i增加1，否则置换i和j对应的值，j减一，当i与j碰头，即说明第一轮递归结束，mid值把数组分为两个部分，前面一部分的值小于等于mid，后面的值大于等于mid，再递归的把这两段进行排序即可：

```
func qsort(arr []int) {
	if len(arr) <= 1 {
		return
	}
	mid := arr[0]
	begin, end := 0, len(arr)-1
	for i := 1; i <= end; {
		if (arr[i] < mid) {
			arr[i], arr[begin] = arr[begin], arr[i]
			begin++
			i++
		} else {
			arr[i], arr[end] = arr[end], arr[i]
			end--
		}
	}
	qsort(arr[:begin])
	qsort(arr[begin+1:])
}
```
平均复杂度O(nlogn)，最坏O(n^2)


### 如何创建一个队列，优先队列，最大（小）堆？
队列是先进先出，可以用双向链表来实现[https://github.com/mangoqiqi/Golang-learning/blob/master/main/queue.go](https://github.com/mangoqiqi/Golang-learning/blob/master/main/queue.go)

优先队列可以用链表来做[https://github.com/mangoqiqi/Golang-learning/blob/master/main/priority_queue_list.go](https://github.com/mangoqiqi/Golang-learning/blob/master/main/priority_queue_list.go)

优先队列堆的实现方法即最大堆[https://github.com/mangoqiqi/Golang-learning/blob/master/main/priority_queue_heap.go](https://github.com/mangoqiqi/Golang-learning/blob/master/main/priority_queue_heap.go)

### 什么是哈希表，冲突如何解决？

参考[https://draveness.me/golang/docs/part2-foundation/ch03-datastructure/golang-hashmap/](https://draveness.me/golang/docs/part2-foundation/ch03-datastructure/golang-hashmap/)

## :computer: 操作系统

### 进程、线程、协程的区别

参考[https://www.jianshu.com/p/f11724034d50](https://www.jianshu.com/p/f11724034d50)

### Linux常用信号（SIG）

### 存储卷的概念？

### 软连接、硬链接分别是什么？

### select和epoll的区别？

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
回表查询简单地说就是，第一次查询只查到了一部分，需要再次查询。解决办法是增加联合索引等

[参考这篇文章](https://www.cnblogs.com/myseries/p/11265849.html)

### SQL注入是啥？怎么避免？
SQL注入就是一种通过操作输入来修改后台SQL语句达到代码执行进行攻击目的的技术。

避免：

1.应使用基于角色的权限控制。严格限制Web应用的数据库的操作权限，给此用户提供仅仅能够满足其工作的最低权限，从而最大限度的减少注入攻击对数据库的危害。

2.所有用户输入都是不可信的。检查输入的数据是否具有所期望的数据格式，严格限制变量的类型，例如使用regexp包进行一些匹配处理，或者使用strconv包对字符串转化成其他基本类型的数据进行判断。

3.对进入数据库的特殊字符（'"\尖括号&*;等）进行转义处理，或编码转换。Go 的text/template包里面的HTMLEscapeString函数可以对字符串进行转义处理。

4.不要直接拼接SQL语句，所有的查询语句建议使用数据库提供的参数化查询接口。例如使用database/sql里面的查询函数Prepare和Query，或者Exec(query string, args ...interface{})。

5.使用专业工具检测，在应用发布之前建议使用专业的SQL注入检测工具进行检测，以及时修补被发现的SQL注入漏洞。网上有很多这方面的开源工具，例如sqlmap、SQLninja等。

6.避免网站打印出SQL错误信息，比如类型错误、字段不匹配等，把代码里的SQL语句暴露出来，以防止攻击者利用这些错误信息进行SQL注入。

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

参考 [https://draveness.me/golang/docs/part3-runtime/ch06-concurrency/golang-goroutine/](https://draveness.me/golang/docs/part3-runtime/ch06-concurrency/golang-goroutine/)

### go的GC如何工作的？

### 如何处理内存泄漏？

### go并发编程实现：一个查询功能，要求1.有1000并发数限制 2.有一个协程查到结果立马返回结束 3.每个线程都有超时时间10s

## :sparkles: Redis

### 如何设计发送短信验证码，要求1分钟内只能发1次，5分钟内最多能发2次，10分钟内最多能发3次？


### :truck: Docker & K8s

### pod是如何做到优雅的退出的?

这篇文章：[https://aleiwu.com/post/tidb-opeartor-webhook/](https://aleiwu.com/post/tidb-opeartor-webhook/)

主要方法：pre-stop-hook、ValidatingAdmissionWebhook

### k8s有哪些组件？分别干什么用的？

Master：api-server、etcd、controller、scheduler
Node：kubelet、kube-proxy

### kubectl logs的流程？
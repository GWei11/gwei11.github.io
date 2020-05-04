---
title: Thread和Object中几个与线程相关的重要方法
categories:
	- [java, 多线程]
tags:
	- java
	- 多线程
---

首先先来看几个问题

1. 为什么`wait`，`notify`和`notifyAll`是定义在`Object`中，而`sleep`是定义中`Thread`中
	1. 因为前面单个方法是与锁相关的，而锁是与对象相关的，而不是与线程相关的。
2. 如何使用多种方式来实现生产者和消费者模式
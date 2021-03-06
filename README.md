![ElemeFE-background](https://github.com/ElemeFE/node-interview/blob/master/assets/ElemeFE-background.png)

# 如何通过饿了么 Node.js 面试

Hi, 欢迎来到 ElemeFE, 如标题所示本教程的目的是教你如何通过饿了么大前端的面试, 职位是 2~3 年经验的 Node.js 服务端程序员, 如果你对这个职位感兴趣或者学习 Node.js 一些进阶的内容, 那么欢迎阅读.

需要注意的是, 本文针对的并不是零基础的同学, 你需要有一定的 JavaScript/Node.js 基础, 并且有一定的工作经验. 另外本教程的重点更准确的说是服务端基础中 Node.js 程序员需要了解的部分.

如果你觉得大多不了解, 就不用投简历了 <del>(这样两边都节约了时间)</del>, 如果你觉得大都有了解或者***光看大纲都都觉得很简单那么欢迎投递简历至 ElemeFe (fe.job@ele.me)***.

### 导读

虽然说目的是要通过面试, 但是本教程并不是简单的把所有面试题列出来, 而<font color="red">主要是将面试中需要确认你是否懂的点列举出来</font>, 并进行一定程度的讨论.

本文将一些常见的问题划分归类, 每类标明涵盖的一些`覆盖点`, 并且列举几个`常见问题`, 通常这些问题都是 2~3 年工作经验需要了解或者面对的. 如果你对某类问题感兴趣, 或者想知道其中列举问题的答案, 可以通过该类下方的 `阅读更多` 查看更多的内容.

整体上大纲列举的并不是很全面, 细节上覆盖率不高, 很多讨论只是点到即止, 希望大家带着问题去思考.

## [Js 基础问题](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md)

### 覆盖点

* [`[Basic]` 类型判断](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#类型判断)
* [`[Basic]` 作用域](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#作用域)
* [`[Basic]` 引用传递](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#引用传递)
* [`[Basic]` 内存释放](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#内存释放)
* [`[Basic]` ES6 新特性](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#es6-新特性)

### 常见问题

* js 中什么类型是引用传递, 什么类型是值传递? 如何将值类型的变量以引用的方式传递? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#q-value)
* js 中， 0.1 + 0.2 === 0.3 是否为 true ? 在不知道浮点数位数时应该怎样判断两个浮点数之和与第三数是否相等？
* const 定义的 Array 中间元素能否被修改? 如果可以, 那 const 的意义是? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#q-const)
* Javascript 中不同类型以及不同环境下变量的内存都是何时释放? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md#q-mem)

[阅读更多](https://github.com/ElemeFE/node-interview/blob/master/sections/js-basic.md)

## [模块](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md)

> 与前端 Js 不同, 后端是直面服务器的, 更加偏向内存方面, 对于一些更基础的问题也会更加关注.

* [`[Basic]` 模块机制](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md#模块机制)
* [`[Basic]` 热更新](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md#热更新)
* [`[Basic]` 上下文](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md#上下文)

### 热更新
分为三个层面的事：

* 代码层面： require cache 来实现
* 框架层面：主要观注点：（1）处理旧的流量，处理完成后退出，（2）不再进入新的流量，（3）新建进程，（4）新流量进入新的进程
* 架构层面：使用反向代理来实现：（1）tcp 实现，（2）http实现，（3）DNS实现。主要从代理中摘除老的代码机，更新完成后，加入新的代码机。

相关链接：

* [Node.js Web应用代码热更新的另类思路](http://fex.baidu.com/blog/2015/05/nodejs-hot-swapping/)
* [NodeJS Web 服务平滑升级](http://frontenddev.org/link/nodejs-web-service-smooth-upgrade.html)
* [nodejs中正确关闭http server的方法](http://www.html-js.com/article/The-correct-method-of-HTTP-server-nodejs-scrap-off-in-nodejs)

### 常见问题

* a.js 和 b.js 两个文件互相 require 是否会死循环? 双方是否能导出变量? 如何从设计上避免这种问题? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md#q-loop)
* 如果 a.js require 了 b.js, 那么在 b 中定义全局变量 `t = 111` 能否在 a 中直接打印出来? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md#q-global)
* 如何在不重启 node 进程的情况下热更新一个 js/json 文件? 这个问题本身是否有问题? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md#q-hot)

[阅读更多](https://github.com/ElemeFE/node-interview/blob/master/sections/module.md)

## [事件/异步](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md)

* [`[Basic]` Promise](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#promise)
* [`[Doc]` Events (事件)](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#events)
* [`[Doc]` Timers (定时器)](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#timers)
* [`[Point]` 阻塞/异步](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#阻塞异步)
* [`[Point]` 并行/并发](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#并行并发)

### 常见问题

* Promise 中 .then 的第二参数与 .catch 有什么区别? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#q-1)
* Eventemitter 的 emit 是同步还是异步? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#q-2)
* 如何判断接口是否异步? 是否只要有回调函数就是异步? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#q-3)
* nextTick, setTimeout 以及 setImmediate 三者有什么区别? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#q-4)
* 如何实现一个 sleep 函数? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#q-5)
* 如何实现一个异步的 reduce? (注:不是异步完了之后同步 reduce) [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md#q-6)

[阅读更多](https://github.com/ElemeFE/node-interview/blob/master/sections/event-async.md)

## [进程](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md)

* [`[Doc]` Process (进程)](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#process)
* [`[Doc]` Child Processes (子进程)](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#child-process)
* [`[Doc]` Cluster (集群)](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#cluster)
* [`[Basic]` 进程间通信](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#进程间通信)
* [`[Basic]` 守护进程](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#守护进程)

### 常见问题

* 进程的当前工作目录是什么? 有什么作用? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#q-cwd)
* child_process.fork 与 POSIX 的 fork 有什么区别? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#q-fork)
* 父进程或子进程的死亡是否会影响对方? 什么是孤儿进程? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#q-child)
* cluster 是如何保证负载均衡的? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#how-it-works)
* 什么是守护进程? 如何实现守护进程? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md#守护进程)

[阅读更多](https://github.com/ElemeFE/node-interview/blob/master/sections/process.md)


## [IO](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md)

* [`[Doc]` Buffer](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#buffer)
* [`[Doc]` String Decoder (字符串解码)](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#string-decoder)
* [`[Doc]` Stream (流)](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#stream)
* [`[Doc]` Console (控制台)](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#console)
* [`[Doc]` File System (文件系统)](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#file)
* [`[Doc]` Readline](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#readline)
* [`[Doc]` REPL](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#repl)

### 常见问题

* Buffer 一般用于处理什么数据? 其长度能否动态变化? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#buffer)
* Stream 的 highWaterMark 与 drain 事件是什么? 二者之间的关系是? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#缓冲区)
* Stream 的 pipe 的作用是? 在 pipe 的过程中数据是引用传递还是拷贝传递? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#pipe)
* 什么是文件描述符? 输入流/输出流/错误流是什么? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#file)
* console.log 是同步还是异步? 如何实现一个 console.log? [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#console)
* 如何同步的获取用户的输入?  [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#如何同步的获取用户的输入)
* Readline 是如何实现的? (有思路即可) [[more]](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md#readline)

[阅读更多](https://github.com/ElemeFE/node-interview/blob/master/sections/io.md)

## Network

### 常见问题

* HTTP 协议中的 POST 和 PUT 有什么区别?
* `TCP/UDP` 的区别? `TCP` 粘包是怎么回事，如何处理? `UDP` 有粘包吗?
* `time_wait` 是什么情况?出现过多的 `close_wait` 可能是什么原因?
* socket hang up 是什么意思? 一般什么情况下出现?
* 列举几个提高网络传输速度的办法?

`更多整理中`

## OS

* `[Doc]` TTY
* `[Doc]` OS (操作系统)
* `[Doc]` 命令行参数
* `[Basic]` 负载
* `[Basic]` 指标
* `[Point]` CheckList

### 常见问题

* 服务器负载是什么概念? 如何计算负载?
* ulimit 是用来干什么的?

`更多整理中`

## 错误处理/调试/优化

* `[Doc]` Errors (异常)
* `[Doc]` Domain (域)
* `[Doc]` Debugger (调试器)
* `[Doc]` C/C++ 插件
* `[Doc]` V8
* `[Point]` 内存快照
* `[Point]` CPU剖析

### 常见问题

* 怎么处理未预料的出错?用 try/catch ，domains 还是其它什么?
* domain 的原理是? 为什么要弃用 domain?
* 为什么要在 cb 的第一参数传 error? 为什么有的 cb 第一个参数不是 error, 例如 http.createServer?

`更多整理中`

## 测试

* `[Basic]` 单元测试
* `[Basic]` 基准测试
* `[Basic]` 集成测试
* `[Doc]` Assert (断言)
* `[Module]` 常见测试工具
* `[Module]` 常见断言工具

### 常见问题

* 为什么要写测试? 写测试是否会拖累开发进度?
* 单元测试的单元是指什么? 什么是覆盖率?
* 测试是如何保证业务逻辑中不会出现死循环的?
* mock 是指什么? 一般如何实现?

`更多整理中`

## util

* `[Doc]` URL
* `[Doc]` Path (路径)
* `[Doc]` Utilities (实用函数)
* `[Doc]` Query Strings (查询字符串)
* `[Basic]` 正则表达式

* 如何获取某个文件夹下所有的文件名?

`更多整理中`

## 存储

* `[Point]` Sql
* `[Point]` NoSql
* `[Point]` 缓存
* `[Point]` 数据一致性

### 常见问题

* 索引有什么用，大致原理是什么?设计索引有什么注意点?
* Session/Cookie 有什么区别?
* 连接超时有可能是什么问题导致的?
* 什么情况下数据会出现脏读? 如何避免?

`更多整理中`

## 安全

* `[Point]` XSS
* `[Point]` CSRF
* `[Point]` 中间人攻击
* `[Point]` Sql/Nosql 注入攻击
* `[Doc]` Crypto (加密)

### 常见问题

* CSRF 的攻击和防范方法?
* 加密如何保证用户密码的安全性?
* 如何避免中间人攻击?

`更多整理中`

---
title: RabbitMQ - 顺序消息
categories:
- 中间件
date: 2017-05-29 
tags:
- RabbitMQ
---
#### 什么是顺序消息

消息有序指的是可以按照消息的发送顺序来消费。

#### 如何实现

publisher - broker - consumer 一一对应的关系，可以保证顺序消费。
这样处理，并行度就会成为消息系统的瓶颈。
应该将根据业务主体将消息分片，比如根据订单id分片。
不同的订单消息，进入不同的队列。同一订单消息，进入唯一匹配的队列。
使用分区顺序消息，既保证业务的顺序，同时又能保证业务的高性能。


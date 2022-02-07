# 第 9 章 发送异步消息

本章内容：

* 异步消息
* 使用 JMS、RabbitMQ 和 Kafka 发送消息
* 从 Broker 拉取消息
* 监听消息

现在是星期五下午 4 点 55 分。您还有几分钟就要开始期待已久的假期了。虽然您有足够的时间开车去机场赶飞机，但是在您打包好行李准备离开的时候，您需要确保您的老板和同事们知道您当前工作的状态，这样下周一他们可以从您中断的地方接着做。不幸的是，您的一些同事已经提前离开去过周末了，并且您的老板一直在开会。您该怎么做呢？

最实用的办法就是，向老板和同事发一封简短的电子邮件，详细说明您的工作进展情况，并承诺寄张明信片。这样做既能传达您的工作的进度，又能赶上飞机。您不知道他们在哪里，也不知道他们什么时候会读这封邮件，但您知道他们最终会回到自己的办公桌上读到这封邮件。与此同时，您正在去机场的路上。

_同步_ 通信有它的适用场景，这是我们在 REST 中所看到的。但这并不是开发人员可以使用的惟一的应用程序间通信方式。_异步_ 消息传递是一种间接地将消息从一个应用程序发送到另一个应用程序而无需等待响应的方式。这种间接方式解耦了相互通信的应用程序，并带来了更好的伸缩性。

在本章中，将使用异步消息传递，把订单从 Taco Cloud 网站发送到另一个独立应用程序 Taco Cloud 厨房，在那里将准备 tacos。我们分别考虑 Spring 为异步消息传递提供的三个选项：Java 消息服务（JMS）、RabbitMQ 和高级消息队列协议（AMQP）以及 Apache Kafka。除了基本的消息发送和接收之外，我们还将了解 Spring 对消息驱动 POJO 的支持：一种类似于 EJB 的消息驱动 bean（MDB）的消息接收方式。

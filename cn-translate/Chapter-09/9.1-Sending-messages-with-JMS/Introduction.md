## 9.1 使用 JMS 发送消息

JMS 是一个 Java 标准，它定义了一个用于使用消息代理的公共 API。自 2001 年首次引入以来，JMS 一直是 Java 中异步消息传递的首选方法。在 JMS 之前，每个消息代理都有一个专用 API，这使得应用程序的消息代码在代理之间的可移植性更差。但是有了 JMS，所有兼容的实现都可以通过公共接口进行处理，这与 JDBC 为关系数据库操作提供公共接口的方式非常相似。

Spring 通过称为 JmsTemplate 的基于模板的抽象来支持 JMS。使用 JmsTemplate，很容易从生产者端跨队列和主题发送消息，并在消费者端接收这些消息。Spring 还支持消息驱动 POJO 的概念：简单的 Java 对象以异步方式对队列或主题上到达的消息做出响应。

我们将探讨 Spring 的 JMS 支持，包括 JmsTemplate 和消息驱动 POJO。我们的重点是 Spring 对 JMS 消息发送的支持，但是如果您想知道更多关于 JMS 的信息，可以阅读由 Bruce Snyder、Dejan Bosanac 和 Rob Davies 合著的《ActiveMQ 实战》一书（Manning 出版社，2011）。

在可以发送和接收消息之前，需要一个消息代理，它可以在生产者和消费者之间传递这些消息。让我们通过在 Spring 中设置消息代理来开始对 Spring JMS 的探索。



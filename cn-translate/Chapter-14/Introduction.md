# 第 14 章 使用 RSocket

本章内容：
* 使用 RSocket 进行响应式网络通信
* 使用 RSocket 的四种通信模型
* 在 WebSocket 上进行 RSocket 传输

曾经有一段时期，在电话和现代电子技术出现之前，与远在他乡的朋友和家人最好的沟通方式是写一封信，然后把信投到邮箱里。这不是一种快速的沟通方式，需要几天甚至几周才能收到回信。但这是一种有效的方式，而且是唯一的选择。

多亏了亚历山大·格雷厄姆·贝尔（Alexander Graham Bell）发明了电话。电话提供了一种与远方朋友和家人交流的新方式，这是一种近实时的异步通信方式。电话发展得相当快，从贝尔先生的第一项发明开始有一段时间了，但它仍然是一种保持联系的流行方式，几乎没有人再写信了。

当涉及到应用程序之间的通信时，由 HTTP 和 REST 服务提供的`请求/响应`模式非常常见，但也有其局限性。就像写信一样，`请求/响应`要先发送消息，然后等待响应。这种模式不容易提供异步通信。在异步通信模式中，服务器可能会以数据流进行响应，或允许开放双向通道，客户端和服务器可以在该通道上相互反复发送数据。

在本章中，我们将介绍 RSocket。这是一种相对较新的应用程序间协议，不仅仅提供简单的`请求/响应`通信模式。因为它天然是响应式的，所以它可以比阻塞式的 HTTP 请求更高效。

在此过程中，我们将了解如何使用 Spring 开发 RSocket 通信。首先，让我们深入了解 RSocket 与基于 HTTP 的通信有哪些区别。
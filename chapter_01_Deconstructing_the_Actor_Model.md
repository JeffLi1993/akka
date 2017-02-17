Deconstructing the Actor Model
##解构角色模型

In 1973, Carl Hewitt, along with Peter Bishop and Richard Steiger, set out to help solve some of these problems in a paper called “Universal Modular Actor Formalism for Artificial Intelligence.” Although many programming paradigms are based around mathematical models, the Actor Model was, according to Hewitt, inspired by physics. It has evolved over the years, but the fundamental concepts have stayed the same.
早在1973年，Carl Hewitt, Peter Bishop和Richard Steiger为了帮助解决这些问题，一起编写了《用于人工智能的通用模块化角色形式体系》。虽然很多编程范式是基于数学模型的，但角色模型是基于来自物理学的Hewitt。它演变了很多年，但基本概念保持不变。

It is important to understand that when working with Akka, you can write code without using the Actor Model. The fact that you are using actors does not imply that you are using the Actor Model. There are many developers who have been using Akka for years and are unaware of the Actor Model.
很重要的是，使用Akka编写代码时，你不需要关心是否使用了角色模型。使用角色，并不意味着真正使用了角色模型。很多开发人员多年使用了Akka，但并不知道角色模型。

The difference between using the Actor Model and simply using actors is the way that you treat those actors. If you use those actors as the top-level building blocks, such that all code in your system resides within a system of actors, you are using the Actor Model. On the other hand, if you build your system such that you have actors resid‐ ing within nonactors, then you are not using the Actor Model.
使用角色模型和简单使用角色的区别在于你对待角色的方式。如果这些角色所属于顶级构建模块，以便于该系统所有代码都编写在同一角色系统中，那么是在使用角色模型。另一方面，如果在非反应器中使用角色去构建系统，那么是没有使用角色模型。

It is also important to understand that programming in the Actor Model is not about any one tool or technology. Entire languages have been written around the idea of the Actor Model. In this way, it is more like a programming paradigm than a set of tools. Learning it is like learning object-oriented programming (OOP) or functional pro‐ gramming. And like those two methodologies, the Actor Model predates Akka, and there are many other implementations of it.
同样很重要的是，基于角色模型的编程并不是一种工具或者技术。所有编程语言都要围绕角色模型的宗旨。这样，它更是一个编程范式而不是一组工具。建议按着学习面向对象编程（OOP）或函数式编程的方式去学习角色模型。类似这两个方法论，角色模型早于 Akka，Akka 是角色模型的一种实现，自然还有很多其他基于角色模型的实现。

The Pony language, for instance, is based on actors and can be easily used to imple‐ ment the Actor Model. Erlang’s processes are equivalent to Akka actors; they are a fundamental feature of Erlang. In Ada, the idea of the Task exists, along with mes‐ sages called “entries”—which are queued by the asynchronous Tasks—meaning the Actor Model can be implemented in this language, as well.
比如，Pony 语言是基于角色，也很容易用于实现角色模型。比如，Erlang 的基本特征是 Erlang 的进程相当于 Akka 角色。还有 ADA 程式语言中，任务的概念也是类似。由异步任务排队被称为“条目”的消息意味着 ADA 也可以实现角色模型。

To implement the Actor Model, there are a few fundamental rules to follow:
• All computation is performed within an actor
• Actors can communicate only through messages
• In response to a message, an actor can:
— Change its state or behavior
— Send messages to other actors
— Create a finite number of child actors
Of course, if you are familiar with Akka, you can immediately recognize how these components have been implemented, but let’s talk about them outside of that context for a moment so that we can better understand how the basic Actor Model might dif‐ fer from the Akka implementation.
要实现角色模型，遵循一些基本规则：
• 所有计算在角色中执行
• 角色之间只能通过消息通信
• 在响应消息中，角色可以做以下操作：
— 改变状态或行为
— 向其他角色发送消息
— 创建有限数量的子角色
如果你很熟悉 Akka，马上就可以认识到这些组件是如何实现的。组件会在另外章节中详细讲解，这里先了解基本的角色模型和 Akka 实现的区别。

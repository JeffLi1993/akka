All Computation Is Performed Within an Actor
##所有计算在角色中执行

Carl Hewitt called the actor the fundamental unit of computation.1 What does it mean to be the fundamental unit of computation? It means that when you build a sys‐ tem using the Actor Model, everything is an actor. Whether you are computing a Fibonacci sequence or maintaining the state of a user in your system, you do so within an actor, or multiple actors.
Carl Hewitt 称角色是计算的基本单元。1 计算的基本单元意味着什么？就是当你使用角色模型构建系统时，每个事物都是一个角色。在一个角色或者多个角色中，都可以进行计算斐波那契（Fibonacci）序列或者维护系统中用户的状态。

批注 1
For more on this, see the video “Hewitt, Meijer and Szyperski: The Actor Model (everything you wanted to know...)”.
更多请看这个视频“Hewitt, Meijer and Szyperski: The Actor Model (everything you wanted to know...)”。

This idea that everything is an actor is not without difficulties, though. If every com‐ putation needs to happen within an actor, this implies that every function and every state variable could be its own actor. And even though this is technically possible, it’s not always pragmatic. Often, we have groups of related functions and it is usually more convenient to wrap all those functions within a single actor. Doing so doesn’t violate the Actor Model. But how do we decide where to draw the line? We will dis‐ cuss this in more detail in Chapter 3 when we learn about domain-driven design (DDD). The building blocks we introduce for DDD are excellent candidates to turn into actors and we can use them as guiding principles for when to create a new actor.
每个事物都是一个角色，这个想法并非没有困难。每个计算都需要在一个角色中发生，那么每个函数和状态变量都是角色。这个技术上是可行的，但并不是那么实际。通常可以定义相关函数的组，这些函数或韩函数组可以包装在单个角色中。这不违背角色模型。这个界限线划分在哪？了解领域驱动设计（DDD）后，在第三章详细讨论这个问题。所介绍的 DDD 构件是实现角色优秀的候选人。因此使用 DDD 可以作为创建新角色的指导原则。

Actors in the Actor Model embody not only state but also behavior. This might sound suspiciously like the definition of OOP—in fact the two are very closely related. Alan Kay, who coined the term “object-oriented programming” and was one of the original creators of the Smalltalk language, was largely influenced by the Actor Model. And while Smalltalk and OOP eventually evolved away from their Actor Model roots, many of the basic principles of the Actor Model remain in our modern interpretation of OOP. In truth, the original focus of OOP was not the objects themselves but rather the messages flowing between them.
角色模型中的角色提现了状态和行为。这跟 OOP 的定义有密切的联系。创造面向对象编程（OOP）术语的 Alan Kay，受角色模型的启发，和其团队一起创造了 Smalltalk 语言。虽然经过发展，Smalltalk 语言和 OOP 远离了角色模型的根本。但角色模型中很多的基本原则，都可以在 OOP 中得到解释。比如，OOP 原先的焦点并不是对象本身，而是它们之间的消息。

>OOP models the fundamental unit of computation as an object (an instance of a class), and is familiar to developers coming from Java and similar languages. Functional programming, on the other hand, models computation around functions and their applica‐ tions, and is seen in languages such as Lisp and Haskell.
> Java 或者相关语言的开发人员很熟悉的是， OOP 是将对象（类的实例）作为计算的基本单元模型。另一方面，函数式编程是围绕函数及其应用程序进行模型计算的。这可以在 Lisp 和 Haskell 语言中提现。

Another aspect of the model that is useful for highly concurrent applications is the idea that an actor’s state is isolated. It is never directly exposed to the outside world. We don’t allow actors to look at or modify the state of another actor, except indirectly through messages. This isolation applies equally to the actor’s behavior. The internal methods or mechanisms of the actor are never exposed to other actors. In fact, state and behavior can largely be treated as the same thing within an actor (more on this later).
对于高并发应用有用的模型的另一方面，角色的状态是相互隔离的。即角色的状态是不会暴露在外部。角色是不允许查看或者修改其他角色的状态。但彼此可以通过消息，间接操作。角色的行为和状态一致，也是相互隔离的。即角色的内部方法或者机制是不会暴露给其他角色的。事实上，状态和行为很大程度上可以被视为角色中相同的事物(稍后详述)。

Actors in the model can take many different forms. They can exist as highly technical constructs like a database access layer, or they can be domain-specific constructs like a person or schedule. They can even be used to perform simple mathematical opera‐ tions. Anything in the system that needs to perform any amount of computation is an actor.
模型中的角色的表现形式会很多。角色可以作为高技术构件存在，比如数据库访问层，比如人和计划表这种特定领域的结构。它们甚至可以执行简单的数学运算。在系统中，执行任何多少的计算量的任何事物都是一个角色。

The actor is the fundamental building block in the Actor Model as well as Akka-based applications, as we will see.
所以将会看到，角色是角色模型以及基于 Akka 的应用程序的基本构件。

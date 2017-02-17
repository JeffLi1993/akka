Actors Can Communicate Only Through Messages
##角色之间只能通过消息通信

We have created our actors in an isolated fashion so that they never expose their state or their behavior. This is an important element of the Actor Model. Because we have isolated them in this way, we need to find other ways by which we can communicate with them and learn about the state of the system.
创建角色通过隔离的方式，是为了不向外部暴露角色的状态和行为。这是角色模型重要的原则。因为以这种方式隔离了角色，所以需要找到其他方式与角色通信，并了解系统的状态。

Messages are the backbone of all communication in the Actor Model. They are what enables communication between actors.
在角色模型中，消息是所有通信的骨干。 角色之间基于消息进行通信。

Every actor, when created, is given an address. This address is the entry point for communication with that actor. You cannot use the address to access the actor directly, but you can use it to send messages to that actor.
当创建角色时，新的角色会拥有一个地址。通过这个地址，可以向该角色通信。不允许通过地址直接访问角色，但可以通过地址向角色发送消息。

>Akka separates the concept of an address from a reference. Most actor communication is done using references. Akka actors also have an address that can be used in some circumstances; however, they are generally avoided. Nonetheless, whether you are using a reference or an address, the basic principle is the same: you have a means to locate the mailbox for the actor so that you can deliver a message to it.
>Akka 是区分地址与引用的概念。大部分角色之间是通过引用进行通信的。Akka 角色也有地址是用于某些情况下使用的，但是通常尽量避免使用。尽管如此，无论使用引用或者地址，基本原则是一致的：有一种方法可以定位到角色的邮箱，以便可以向其发送消息。

Messages that are sent to an actor are pieces of immutable data. These messages are sent to a mailbox that exists at the address provided for the destination actor. What happens after the message reaches the mailbox is beyond the control of the sender. Messages can be delivered out of order, or they might not even be delivered at all. The Actor Model provides an At Most Once guarantee of delivery. This means that failure is an option, and if we need to guarantee delivery, we will need other tools to enable that.
已发送给角色的消息是不可变数据。消息将会发送到有提供地址的目标角色的邮箱。放送消息的角色无法已到达的消息。消息可以不按顺序发送，或者甚至根本不发送。角色模型提供了最多一次发送的保证。这意味着失败时是一个选择，如果需要保证发送，将需要其他工具来实现。

>At Most Once delivery is the default guarantee provided by the Actor Model and by Akka. However, At Least Once delivery can be built on top of At Most Once delivery, and there are mechanisms within Akka to provide that.
>Akka further provides a slightly stronger guarantee of ordering. In Akka, message order is guaranteed between any pair of actors. That is, if one actor sends multiple messages to another, we can guaran‐ tee that the order of those messages will be preserved.
>最多一次发送是角色模型和 Akka 提供的默认保证。然而，至少一次发送可以建立在最多一次发送之上，这些是 Akka 内部机制来提供的。
>Akka 还提供了较强的消息顺序保证。在 Akka 中，任何一对角色之间保证了消息的顺序。也就是说，一个角色向另一个角色发送多个消息后，可以保证这些消息的顺序被保存下来。

After the messages are in the mailbox, the actor can receive those messages. However, messages are received one at a time. No single actor can process two messages simul‐ taneously. This is a critical guarantee because it allows us to operate within the actor in a single-threaded illusion. Actors are free to modify their internal state with no wor‐ ries about whether another thread might also be operating on that state. As long as we maintain the single-threaded illusion, our state is protected against any of the normal concerns of concurrency.
消息到达邮箱后，角色可以收到这些消息。但是，每次只能接受一个消息。单个角色不能同时处理两个消息。这是一个关键的保证，因为它允许单线程的想法下，在角色中操作。角色可以自由地修改其内部状态，而不用担心另一个线程是否也在操作这个状态。只要维持单线程的想法，角色的状态就可以防止任何正常的并发问题。

The exact nature of the messages is dependent on the actor’s functionality. For domain actors, it would be common to see the messages as commands or events pre‐ sented by using domain terms like “AddUser” or “CreateProject” in our scheduling example. Of course, if the actor is more technical in nature, the messages can be more technical, like “Save” or “Compute.”
消息的性质取决于角色的功能。对于角色领域，如果在调度示例中，是通过 “AddUser” 或 “CreateProject” 之类的领域术语将消息看做命令或事件。当然，如果角色在本质上更具技术性，消息也可以更具技术性，如 “Save” 或 “计算”。

Figure 1-1. Actors communicating with one another
图 1-1. 角色之间的通信

It is worth mentioning that Akka treats its mailboxes slightly differ‐ ently. The default implementation in Akka provides an ordered mailbox so that you can guarantee that messages will be processed by the actor in the order in which they are placed in the mailbox.
值得一提的是，Akka 对待邮箱的策略有所不同。Akka 默认实现是提供了一个有序的邮箱，这样可以保证角色按照一定的顺序进行处理消息。

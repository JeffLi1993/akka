Actors Can Change Their State or Behavior
## 角色可以改变状态或行为

In addition to sending messages and creating child actors, actors can also change how they will react to the next message. We often use the term “behavior” when talking about how an actor will change, but this is slightly misleading. The change in behav‐ ior, or the change in how an actor will react, can also manifest itself as a change of state.
角色可以发送消息和创建子角色，还可以更改对消息的响应。把角色是如何改变定义为“行为”，这是有点误导的。角色行为的改变，或者角色如何响应的改变，表现为状态的改变。

Let’s consider the scheduling example discussed in the introduction. If we have an actor that represents a person’s availability, the initial state might indicate that this person is available for a project. When a message comes in to assign that person to a project, the actor can alter itself such that when a new message comes in, it will show as unavailable. Even though this seems to be a change in state, we still consider it to be a change to the actor’s behavior because the actor is now behaving like it has a value of unavailable when the next message comes in.
让我们讨论下在介绍章节的调度案例。如果一个角色代表一个用户的适用性，初始状态指示这个用户是否适用于项目。

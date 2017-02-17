Reality Is Eventually Consistent
##现实是最终一致性的

Consider the example of reaching for a cup of coffee. On the surface, this might seem like a very simple example. You reach out and pick up a cup of coffee. Not much is happening there. But let’s look deeper.
思考一个案例，是去拿一杯咖啡。自然，这应该算是最简单的例子。你伸出手，然后拿起这杯咖啡。虽然没有更多的事情可以发生，但让我们往深层次想想。

To be able to pick up the coffee, you need to know where it is. You can look over and see the cup, but are you seeing it as it is, or as it was? The information you use to determine the location of the cup is based on the photons reflected from that cup. Those photons take time to travel. Further, when our eyes receive the data, they must perform some processing before sending the data to our brain. Further processing needs to be done by other areas of our nervous system in order to communicate the desire to move our arm. Finally, our arm must stretch out to take the cup.
首先你得知道咖啡杯子在哪里，你才能够去拿起杯子。再者你可以看看杯子，确定是不是你想要的杯子。最后杯子上反射的光子，可以确定杯子的位置。光子通过一段时间，在空气中传播到我们的眼睛。当我们的眼睛接收到数据时，眼睛将这些数据进行处理后，将其发送到我们大脑。大脑中的神经系统进一步对数据加工处理后，将信号传达到我们手臂。最后才伸出手臂拿起杯子。

At each stage in the process, small amounts of delay have leaked into the system. Picking up a coffee cup is a fairly simple operation, though, in a very static environ‐ ment, so those delays don’t have a large effect. But as the nature of the environment changes, as events begin to happen faster and more frequently, those small delays can add up. Picking up a cup of coffee is fairly trivial. Trying to catch that same cup of coffee if it falls off the table, without spilling it, is much more challenging. Trying to catch multiple cups...well, now we’ve entered the realm of the impossible.
在该过程的每个阶段中，少量的延迟会渗入系统中。拿起咖啡杯是一个相当简单的操作，而且在非常静态的环境中，这些延迟没有产生很大的影响。但是随着环境性质的改变，事件也随着变化的更快和更频繁，更多这些延迟会累计。拿一杯咖啡杯是相当微不足道的。比如更具挑战的是，尝试没有溢出地去拿一杯正在倒的咖啡杯。比如尝试一起拿更多杯...好吧，已经不可能完成了。

The truth is that our reality is bounded by the speed of light. The laws of physics, and the speed of light, put an upper bound on causality. Unless two things occupy the same space (which, of course, is impossible), for one event to have an effect on another, there must be a passage of time between the two. Two observers watching the same event from different distances will experience that event at different times. The person closer to the event will experience it first, while the person further away will experience it slightly later. Yet, despite the difference in time, both experiences are real. Both are equally valid. It is this idea, rooted in physics, on which the Actor Model is based.
事实上，我们还要受到现实中光速的限制。基于物理学规律的因果关系，光的速度是有上限的。除非两个事物占据相同的空间（当然，这是不可能的），因为相互影响的事物之间必须有一段时间。两个观察者在不同的距离观察相同的事物，他们所经历的时间也会不同。靠近事件的人首先体验它，而另一个则晚点体验。尽管经历的时间不同，但是两个事物体验都是真实并且有效的。角色模型就是基于这种来源于物理学的思想。

The truth is that we live our lives operating on out-of-date information. On a small scale, our cells are communicating with one another through messages passed in the form of hormones. On a larger scale, we go through our daily lives talking to people, watching the news, reading the latest developments on a blog. All of these things are in one way or another just a form of asynchronous messaging. In fact, when we break it down, there is nothing in our lives that is being experienced synchronously.
事实上，我们在过时的信息上生活着。在小规模上，我们的细胞通过激素传递进行信息交流。在更大的规模上，我们是这样经历日常生活的。与别人交流，看新闻，阅读博客上最新的开发资讯。所有这些经历都是异步消息传递的一种形式。我们会发现，当往生活的深层次思考，生活中没有什么是同步经历的。

Even our computers behave this way. Every operation a computer performs is done by sending a signal over some kind of medium, whether it’s electrical signals, pho‐ tons, or something else.
我们的计算机也是这样的。计算机通过在某种介质上发送信号来完成操作。无论该信号是电信号，光子或者是其他东西。

So, if everything in the world is being experienced in an asynchronous manner, why do we put so much effort into trying to write software that is synchronous? We teach ourselves that we should model software on the real world, yet we ignore the funda‐ mental concept of time. Wouldn’t it be better if we modeled it on the real world and built our software using asynchronous events or messages?
如果世界上的一切都以异步的方式运行着，为什么我们会付出很大的努力尝试编写同步方式的软件？和前面一样，我们知道应该在真实具体场景上模拟软件，但我们忽略了时间的基本概念。是不是和真实具体场景一样，使用异步事件或者异步消息来构建我们的软件会更好？

As a fun exercise, let’s reverse this idea. Let’s take the real world and model it through the lens of traditional synchronous software. How does this look? What are the consequences?
作为一个有趣的练习，让我们反转思考下这个想法。随着传统同步软件的镜头，让我们采取真实具体场景和模型。这会怎么样？后果是什么？


Let’s go back to our coffee example. When your brain decides that you want a sip of coffee, it must first pause time, at least in a localized fashion. You need to halt the world around you so that you can ensure that nothing changes between the moment you decide to have that coffee and the moment when the coffee reaches your lips. Nothing can interfere with that. If you reach out to take the coffee, only to discover someone else got there first, you have chaos. Instead, you freeze everything around
you, locking the state in place, so that you can guarantee that won’t happen. Anyone else who might have been reaching for that same cup will now be stopped, frozen until you have completed your action. This means not just pausing another person, but also pausing the air, the light, everything around that cup. Everything between the cup and you must stop, or else your state might become invalid. This sounds very complicated, much more complicated than if we had just taken the time to model the system correctly in the first place.
回到拿咖啡杯的例子。当你的大脑决定想要哪一杯咖啡的时候，在本地话方式中，它必须暂停对周围世界的时间。没有什么可以干扰你，以便于确定你决定拥有哪个咖啡及咖啡到你嘴唇那一刻之间没有任何的变化。如果你伸出手去拿咖啡杯，发现其他人先拿走了，你会陷入混乱。相反，你会冻结你周围的一切，让周围保持锁住的状态，以便于你可以保证不会发生。任何可能拿那杯咖啡杯的都会被锁住停止，直到你完成了行动为止。这不单单只是暂停一个人，而且还需要暂停空气，灯光，杯子周围的一切。杯子和你之间的一切都必须停止，否则你的状态可能变得无效。听起来很复杂，但远比我们先前正确的建模系统所花时间复杂的多。

This is one of the fundamentals of the Actor Model—with it, we can build software that reflects how reality actually works instead of assuming a frozen-in-time world that doesn’t actually exist.
这是角色模型的基本原理之一。通过它，我们可以构建反应真实具体场景工作原理的软件，而不是建设在不存在的可以冻结时间的业务场景。

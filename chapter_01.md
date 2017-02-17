The Actor Model
#角色模型

It is essential to understand how actors were meant to be used to realize their full value, and that’s what you will learn in this chapter. Here, we explore actors—how they work, and how they interact with one another and the outside world.
在这一章节，你将会本质上地学习并理解角色模型和其在应用上的价值体现。下面，我们会探讨角色模式是如何工作的，以及内外部角色与角色之间如何相互作用。

Many of the techniques we use to design software teach you that it is important to look at the real world before writing code. We must understand the use case for the software. We need to ask questions about who will be using it and how they will use it. These questions are critical to the design of good software. But in the pursuit of our design, we often forget to ask ourselves an important question: “How long will it take?” Yet, anyone who has written a highly concurrent system knows that time is an integral part of how we develop our software.
许多用于设计软件的技术教会你，在写代码之前必须分析好现实具体业务场景。还有必须了解软件的各个用例。以及要询问有关哪些用户会使用该软件和用户是如何使用它的。这些都是对好的软件设计至关重要的。但是在追求软件设计时，我们常常会忘记一个很重要的问题：“这软件需要编写多少时间？”。然而，参与过编写高并发系统的程序员都明白一个道理，开发时间是开发软件的一个重要组成部分。

Let’s explore a bit far afield from software for a moment—don’t worry, we’ll show how this relates to software development in a moment!
让我们先不再探讨软件开发。但不要担心，我们接下来展示的一切，会与软件开发有所联系。

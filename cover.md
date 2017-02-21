书名：Akka模式
副书名：分布式应用设计实践

《Akka模式：分布式应用设计实践》


Table of Contents
Preface
Conventions Used in This Book
O’Reilly Safari
How to Contact Us
Acknowledgments

1. The Actor Model
Reality Is Eventually Consistent
Deconstructing the Actor Model
-- 2017-02-04 13:44:07
All Computation Is Performed Within an Actor
Actors Can Communicate Only Through Messages
-- 2017-02-07 10:31:39
Actors Can Create Child Actors
2017-02-16 23:59:02 - 2017-02-21
Actors Can Change Their State or Behavior

Everything Is an Actor
Uses of the Actor Model
Defining Clear Boundaries
When Is the Actor Model Appropriate?
Conclusion

2. Introducing Akka
What Is Akka?
Akka Is Open Source
Akka Is Under Active Development
Akka Is Distributed by Design
Akka Components
Akka Actor
Child Actors
Remoting: Actors on Different JVMs
Clustering: Automatic Management of Membership
Akka HTTP
TestKit
Contrib
Akka OSGi
Akka HTTP
Akka Streams
Akka’s Implementation of the Actor Model
Akka’s Actors in the Actor Model
Message Passing
Actor Systems
The Akka Typed Project
Conclusion
3. Distributed Domain-Driven Design
DDD Overview
The Benefits of DDD
Components of DDD
Domain Entities
Domain Value Objects
Aggregates and Aggregate Roots
Repositories
Factories and Object Creation
Domain Services
Bounded Contexts
Conclusion
4. Good Actor Design
Starting Small
Encapsulating State in Actors
Encapsulating State by Using Fields
Encapsulating State by Using “State” Containers
Encapsulating State by Using become
Mixing Futures with Actors
Ask Pattern and Alternatives
Problems with Ask
Accidental Complexity
Alternatives to Ask
Commands Versus Events
Constructor Dependency Injection
actorSelection via Path
Conclusion
5. Good Data Flow
Throughput Versus Latency
Streams
Routers
Mailboxes
Unbounded Mailboxes
Bounded Mailboxes
Work Pulling
Back Pressure
Acks
High-Water Marks
Queue-Size Monitoring
Rate Monitoring
Akka Streams
Source
Sink
RunnableGraph
Flow
Junctions
Back Pressure in Akka Streams
Using Akka Streams
Conclusion
6. Consistency and Scalability
Transactions and Consistency
Strong Versus Eventual Consistency
Concurrency Versus Parallelism
Why Globally Consistent Distributed State Doesn’t Scale
Location Transparency
Delivery Guarantees
At Most Once
At Least Once
Exactly Once Doesn’t Exist (But Can Be Approximated)
How Do You Approximate Exactly Once Delivery?
Cluster Singleton
Scalability
Avoid Global State
Avoid Shared State
Follow the Actor Model
Avoid Sequential Operations
Isolate Blocking Operations
Monitor and Tune
Cluster Sharding and Consistency
Sharding
Sharding in Akka
Shard Key Generation
Shard Distribution
Consistency Boundary
Scalability Boundary
Sharding Aggregate Roots
Persistence
Passivation
Using Cluster Sharding for Consistency
Conclusion
7. Fault Tolerance
Types of Failures
Exceptions
Fatal Errors in the JVM
External Service Failures
Failing to Meet a Service-Level Agreement
Operating System and Hardware-Level Failures
Isolating Failures
Bulkheading
Graceful Degradation
Isolating Failure by Using Akka Cluster
Controlling Failures by Using Circuit Breakers
Dealing with Failures
Dealing with Exceptions (Let It Crash)
Dealing with External Service Failures
Conclusion
8. Availability
Microservices Versus Monoliths
Bounded Contexts as Microservices
Fine-Grained Microservices
Cluster-Aware Routers
Distributed Data
Graceful Degradation
Deployment
Staged Deployment/Rolling Restarts
Blue/Green Deployment
Crash Recovery/Operational Monitoring
Health Checks and Application Status Pages
Metrics
Logging
Watchdog Tools
Conclusion
9. Performance
Isolating Bottlenecks
Tuning Akka
Reduce or Isolate Blocking Sections
Make the Message Process in Less Time
Engage More Actors on Processing the Messages
Dispatchers
The Standard Dispatcher
Pinned Dispatcher
Balancing Dispatcher
Calling-Thread Dispatcher
When to Use Your Own Dispatchers
Increase Parallelism
Conclusion

CountDownLatch是在java1.5被引入的，跟它一起被引入的并发工具类还有CyclicBarrier、Semaphore、
ConcurrentHashMap和BlockingQueue，它们都存在于java.util.concurrent包下。
CountDownLatch这个类能够使一个线程等待其他线程完成各自的工作后再执行。
例如，应用程序的主线程希望在负责启动框架服务的线程已经启动所有的框架服务之后再执行。

CountDownLatch是通过一个计数器来实现的，计数器的初始值为线程的数量。
每当一个线程完成了自己的任务后，计数器的值就会减1。当计数器值到达0时，
它表示所有的线程已经完成了任务，然后在闭锁上等待的线程就可以恢复执行任务。


redlock简介

在不同进程需要互斥地访问共享资源时，分布式锁是一种非常有用的技术手段。
实现高效的分布式锁有三个属性需要考虑：

安全属性：互斥，不管什么时候，只有一个客户端持有锁
效率属性A:不会死锁
效率属性B：容错，只要大多数redis节点能够正常工作，客户端端都能获取和释放锁。
Redlock是redis官方提出的实现分布式锁管理器的算法

http://www.spring4all.com/question/177
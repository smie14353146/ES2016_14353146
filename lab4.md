## Lab4: 死锁 ##


### 实验任务 ###

1. 按步骤写完出相应代码，运行程序，使其发生死锁；
2. 理解发生死锁现象的原因；
### 实验内容 ###

**1. 把下面的代码抄到 Deadlock.java里面,保存**

![](http://p1.bpimg.com/575659/44700f3434e63aec.png)

![](http://p1.bpimg.com/575659/12c831586f68ff92.png)


**2.linux 系统，把下面这段写到记事本里，然后保存为.sh**

![](http://p1.bqimg.com/567571/59e7a4af02562d68.png)

### 实验结果 ###
**1.运行javac Deadlock.java**

![](http://p1.bqimg.com/567571/eb00f71d091a0212.png)

![](http://p1.bqimg.com/567571/4bb9124bdaf3ed0b.png)

**2.运行Deadlock.sh**

![](http://p1.bpimg.com/567571/8bbb293d6e03ddb3.png)
![](http://p1.bqimg.com/567571/f69fc8dbe54850c1.png)

###实验感想###
死锁就是两个或者多个进程，互相请求对方占有的资源。

1.互斥条件：一个资源每次只能被一个进程使用

2.请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放

3.不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺

4.循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系

**这次实验产生死锁的原因**

关键字 synchronized:
当它用来修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多只有一个线程执行该段代码。
当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞。
![](http://p1.bpimg.com/575659/44700f3434e63aec.png)

我们来看主函数的时间轴，调用了new Deadlock（）；Deadlock（）中；A a=new A（）；B b=new B（）；构造函数里，Thread t = …;int count =…;当t.start(),之后，线程t就被插入到调度队列里，当调度到它的时候，就跑run()里面的代码，但是同时也在跑while，当两个线程同时互相申请锁时则发生死锁，多少次停是随机的，我们也可以调节程序中count值，使其发生死锁。

![](http://p1.bpimg.com/575659/12c831586f68ff92.png)



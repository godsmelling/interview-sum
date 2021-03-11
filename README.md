# interview-sum


要求：熟悉网络和多线程编程；熟悉spring boot/mybatis等开源框架；深入理解运行原理
      熟悉分布式编程技术，RPC框架，MQ消息等中间件；
      了解云原生相关技术，如k8s，docker
      熟悉Linux，shell
      
      
做了水平分库，未做分布式事务
  
非关系型数据库：MRS:HBASE+HDFS



微服务：
auditlog：记录服务之间的交互日志
credit：征信平台，提供征信相关数据
h5portal：提供前台服务调用
mqgateway：
notification：通知服务
customerod:透支服务
taskjob：系统任务
usercenter：用户中心
saving：提供存款服务
ussdmenu：提供短信服务配置


技术点：springboot，mybatis，redis，k8s，docker，Apollo，Linux
数据库：mysql



常见题目：
1、java锁有哪些？具体的实现是什么。讲一下CAS算法


2、java单例模式有哪些？
    饿汉
    懒汉
        DCL及可能存在的问题
        用volatile
        
        
        
3、java反射，你用过哪些？
4、计算机网络，三挥手四握手
5、树从根到叶子节点的遍历
6、hashmap的底层数据结构，怎么解决hash冲突，为什么线程不安全。
    ConcurrentHashMap是如何保证线程安全的
7、MySQL的索引结构，为什么是B+树而不是B树
8、java内存模型，堆的组成，GC过程
9、线程池设置了coreSize和maxSize之后，如果线程数量已经达到coreSize，再进来一个任务，会怎么处理？
10、SQL查询优化怎么做？
11、创建一个线程有几种方式？用过哪几种
12、HashSet的底层实现
13、为什么1.8版本会将链表转为红黑树？
14、类加载过程讲一下
15、你们项目中用到的redis都是怎么用的？Redis的持久化方式有哪些
16、讲讲项目为什么要用Hystrix？
17、Spring的启动流程
18、SpringBoot的特点
19、垃圾回收算法讲一下，为什么分新生代和老年代
20、介绍一下常用的集合类。list和set的区别，以及各自实现类和底层实现
21、CopyOnWriteList的特点及实现
22、HashMap的hash函数讲一下，如何确定槽位？
23、Linux的命令用过哪些？awk用过吗？
24、二叉树中序遍历，递归非递归实现

25、微服务之间的通信


讲项目，画架构图，为什么这么设计，负责哪一块内容




1. http协议与https协议 TCP/IP协议
2. spring、spring framework、springboot、springcloud
  2.1 spring framework的IOC和AOP概念
  2.2 springmvc是什么，springmvc和springboot的区别
  2.3 springboot自动装载的原理
  2.4 springcloud部署的整体流程，每个部件的作用（**）
  2.5 消息队列（***）
    2.5.1 消息队列有哪些框架可以应用 各种的优缺点
    2.5.2 生产和消费具体是怎么和消息队列交互的
3. Redis
  3.1 redis如何部署在springboot中
  3.2 redis的日常使用语法
  3.3 redis持久化的两种方法
  3.4 redis的基本配置 超时时间|端口|集群配置|持久化配置
  3.5 redis的优点和缺点
  3.6 redis的数据结构
  3.7 如何解决缓存穿透问题
4. Java
  4.1 Collection
    4.1.1 ArrayList 扩容
    4.1.2 HashMap 线程不安全 底层数据结构 扩容 计算数组下标时的具体hash算法 jdk1.7中hashMap第二层链表可能出现指向错乱的具体场景
    4.1.3 HashTable 线程安全 为什么效率低 
    4.1.4 ConcurrentHashMap 线程安全 对比hashTable为什么效率高 底层数据结构 扩容
    4.1.5 Collections.synchronizedxxx()
    4.1.6 vector
    4.1.7 stack
  4.2 IO
  4.3 Thread
    4.3.1 什么是线程，创建一个线程的方法有哪些
    4.3.2 锁有哪些，哪些效率高，锁升级的过程
    4.3.3 如何调试线程
    4.3.4 线程池的底层实现原理
    4.3.5 线程池创建方法的每个参数的含义
  4.4 JVM
    4.4.1 内存分区 每个区里面存放的是什么（**）
    4.4.2 gc机制 常见的gc算法
    4.4.3 类加载机制 什么是双亲委派机制
    4.4.4 一个对象创建的全过程
    4.4.5 常用的jvm调优插件jmap jconsole等 各自的用途
    4.4.5 如果出现了oom（内存泄漏）异常怎么调优  jmap 查看堆内内存分配，根据线程信息定位到具体代码
  4.5 反射
  4.6 动态代理
  4.7 设计模式
    4.7.1 常见的设计模式
    4.7.2 单例模式 dcl
5.Mysql
  5.1 常用语法
  5.2 表连接
  5.3 视图
  5.4 存储过程
  5.5 自定义函数
  5.6 如何调优
  5.7 数据隔离的四种层次（*）
  5.7 主键索引和普通索引的区别（功能和底层数据结构）
  5.8 联合索引生效失效场景
6.Nginx（目前没问过）
  6.1 反向代理
  6.2 负载均衡
  6.3 动静分离
7.RPC
  7.1 RPC是什么，主要的内容
  
/***/
  针对项目经验的问题
  1.如果两个客户端同时新增了一个产品，后台怎么做幂等处理。
  2.在多集群情况下，如果两个客户端同时新增了一个产品，且命中了两个不同集群的服务，如果做幂等处理
  3.mq中的消息如果被消费失败了怎么办
  4.mq中的消息失败了采用重发机制，如果一直失败怎么办
  5.项目中你解决的困难问题或者能展现你技术的问题（会针对的提问）
  6.项目中重构代码具体是怎么重构的

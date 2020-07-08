# 小姐姐java提问

### 低级
* 乐观锁，悲观锁的区别
```
悲观锁：当请求来时，将资源锁住，在执行请求，后续请求，只能排队
乐观锁：当请求来时，先执行请求，执行失败后则返回错误
```
* 公平锁、非公平锁的区别
```
公平锁是指每次访问资源时，都会排队
非公平锁值每次访问资源时，直接竞争，不会排队，也可理解为插队
```
* java中int类型有几个字节
```
4
```
* mysql的索引的数据结构是什么
```
B+树
```

### 中级
* redis的大key危害有哪些
```
1.导致redis阻塞，性能过慢
2.网络拥塞，网络过慢
3.过期删除，内存抖动
```
* jdk1.8中，HashMap中默认负载因子是多少，是否可以修改，在ConcurrentHashMap中是否可以修改
```
HashMap的默认负载因子是0.75，可以修改
ConcurrentHashMap的默认负载因子也是0.75，但是不可以修改
```
* jvm中标记整理算法解决了标记清除算法什么问题
```
解决了标记清除算法会产生大量不连续的碎片
```
* hashmap在什么时候初始化数组
```
在putVal的时候会判断数组是否是null，table为null时会构造数组
```
* jvm中的内存构造有哪些结构，哪些是线程私有，哪些是线程共有
```
堆，栈，本地方法栈、方法区，程序计数器(pc寄存器)，
栈，本地方法栈、程序计数器(pc寄存器)是线程私有
堆，方法区是线程共有
```
* 如果表中联合索引有三个字段A、B、C，下列语句是否使用到索引，
```
select * from 表 where B=xxx AND C=xxx
否
select * from 表 where A like "%xxx"
否
select * from 表 where A=xxx AND B>xxx AND B<xxx  AND C=xxx
会使用到索引，但是只会使用到一部分，即A这一列
```
* mysql中可重复读解决了读已提交什么问题，通过什么解决
```
解决了可重复读的问题，通过mvcc机制解决
```

### 高级
* Spring中解决循环依赖有几层缓存
```
3层
```
* 简要说明Spring中的BeanPostProcessor接口中有哪几个方法及其作用
```
BeanPostProcessor作用是在bean初始化前后执行定制方法，有两个方法
postProcessBeforeInitialization和postProcessAfterInitialization
postProcessBeforeInitialization在bean初始化前执行，
postProcessAfterInitialization在bean初始化后执行
```
* 在redis中如果同时执行BGREWRITEOF和BGSAVE操作会怎样
```
引发大量磁盘写入操作，降低性能
```
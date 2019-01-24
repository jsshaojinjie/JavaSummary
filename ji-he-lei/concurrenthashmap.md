# 1.分段锁原理

ConcurrentHashMap是将锁的细度降低从而提高性能。

先使用Wang/Jenkins hash的变种算法对元素的hashCode进行一次再哈希，将数据均与的分布在segment

![](/assets/400827-20170928212457434-1134706220.png)






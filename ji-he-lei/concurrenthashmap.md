# 1.分段锁原理

ConcurrentHashMap是先将key计算hash值，然后根据hash值进行加锁，将锁的细度降低从而提高性能。


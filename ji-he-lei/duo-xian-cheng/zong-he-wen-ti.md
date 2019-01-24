# 1.线程池有哪几种

常用的有四种：

* newCachedThreadPool
  当线程池中没有空闲线程进行调用时，则创建一个新的线程；如果线程池中有线程长时间进行空闲（默认60s），则进行销毁；线程池的最大大小为Integer的最大值。

* newFixedThreadPool
  线程池创建固定数量的线程，线程池中的线程与线程池的生命周期一样，不会自动销毁。
* newSingleThreadExecutor
  只有一个线程的线程池。
* newScheduleThreadPool
  创建一个固定线程数量的，可定时以及周期性执行的线程池。




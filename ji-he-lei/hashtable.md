# 1.key与value是否可以为null

都不能为null;

put操作时，需要去key的hash值，但是null没有，而且value会对是否为null进行判断，如果时null， 则抛出异常。

![](/assets/import2.png)


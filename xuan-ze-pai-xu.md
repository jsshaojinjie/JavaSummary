时间复杂度：最好情形O\(n^2\)，平均情形O\(n^2\)，最差情形O\(n^2\)

空间复杂度：O\(1\)

稳定性：不稳定

基本思想：每次从队列中选择最大（最小）的数据与数组末尾交换，然后数组长度减一

```
    public static void sort(int[] array) {
        if (array.length == 0) return;
        for (int i = 0; i < array.length; i++) {
            int index = i;
            for (int j = i + 1; j < array.length; j++) {
                if (array[j] < array[index]) {
                    index = j;
                }
            }

            if (i != index) {
                array[i] = array[i] + array[index];
                array[index] = array[i] - array[index];
                array[i] = array[i] - array[index];
            }
        }
    }
```




时间复杂度：O\(n\)~O\(n^2\)

空间复杂度：O\(1\)

稳定性：不稳定

基本思想：通过重复循环数组，每次比较左右两个数据，按照大小规则进行替换，没循环一次，都能在数组尾部获得最大的（或最小）的数据。

```
    public static void sort(int[] array) {
        for (int i = array.length - 1; i > 0; i--) {
            for (int j = 0; j < i; j++) {
                if (array[j] > array[j + 1]) {
                    array[j] = array[j] + array[j + 1];
                    array[j + 1] = array[j] - array[j + 1];
                    array[j] = array[j] - array[j + 1];
                }
            }
        }
    }
```




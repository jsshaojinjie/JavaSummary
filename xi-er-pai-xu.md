时间复杂度：O\(n\)~O\(n^2\)

空间复杂度：O\(1\)

稳定性：不稳定

基本思想：每次根据块间隔距离将数组分成多个块，每个块进行排序，可以使用插入排序，然后缩小块距离，最终到块的距离为1截止。

```
    public static void sort(int[] array) {
        if (array.length == 0) return;
        int section = array.length / 2;
        while (section >= 1) {
            for (int i = section; i < array.length; i++) {
                int temp = array[i];
                int j = i - section;
                while (j > 0 && array[j] > temp) {
                    array[j + section] = array[j];
                    j = j - section;
                }
                array[j + section] = temp;
            }
            section = section / 2;
        }
    }
```




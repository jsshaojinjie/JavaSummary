时间复杂度：O\(nlgn\)

空间复杂度：O\(1\)

稳定性：不稳定

基本思想：首先从非叶子节点开始向上循环，每次比较自己与左右子节点的大小，选择最大（或者最小）的节点与此节点交换，最终根节点为堆中最大（或者最小）的节点，将此节点与最后的一个节点交换，然后堆节点数量减一，再重复循环操作。

```
    public static void sort(int[] array) {
        if (array.length == 0) return;

        for (int i = array.length-1; i > 0; i--) {
            maxHeap(array, i);
            array[i] = array[i] + array[0];
            array[0] = array[i] - array[0];
            array[i] = array[i] - array[0];
        }
    }

    //将数组前length长度的数据排序城大数据堆（根节点最大）
    private static void maxHeap(int[] array, int lastIndex) {
        //从第一个非叶子节点开始
        for (int i = (lastIndex - 1) / 2; i >= 0; i--) {
            int leftIndex = 2 * i + 1;
            int rightIndex = 2 * i + 2;
            rightIndex = rightIndex > lastIndex ? leftIndex : rightIndex;
            int maxChildIndex = array[leftIndex] > array[rightIndex] ? leftIndex : rightIndex;

            if(array[maxChildIndex]>array[i]){
                array[i] = array[i] + array[maxChildIndex];
                array[maxChildIndex] = array[i] - array[maxChildIndex];
                array[i] = array[i] - array[maxChildIndex];
            }
        }
    }
```




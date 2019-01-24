时间复杂度：O\(nlgn\) ~ O\(n^2\)

空间复杂度：O\(nlgn\)

稳定性：不稳定

基本思想：将数组头部数据作为基数，将数组改为小于等于基数与大于基数的两部分，放在基数左右两边，然后递归操作左右两边数组

```
    public static void sort(int[] array) {
        if (array.length == 0) return;
        sort(array, 0, array.length - 1);
    }

    private static void sort(int[] array, int left, int right) {
        if (left >= right) return;
        int base = array[left];
        int leftIndex = left;
        int rightIndex = right;
        while (left < right) {
            while (left < right && array[right] > base) {
                right--;
            }

            while (left < right && array[left] <= base) {
                left++;
            }
            if (left < right) {
                array[left] = array[left] + array[right];
                array[right] = array[left] - array[right];
                array[left] = array[left] - array[right];
            }
        }

        if (left != leftIndex) {
            array[left] = array[left] + array[leftIndex];
            array[leftIndex] = array[left] - array[leftIndex];
            array[left] = array[left] - array[leftIndex];
        }

        sort(array, leftIndex, left - 1);
        sort(array, left + 1, rightIndex);
    }
```




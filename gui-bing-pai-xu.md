时间复杂度：O\(nlgn\)

空间复杂度：O\(nlgn\)

稳定性：稳定

基本思想：将数组分为两块，分别对两块进行排序，然后合并这两个有序数组。

```
    public static void sort(int[] array) {
        if (array.length == 0) return;
        sort(array, 0, array.length - 1);
    }

    private static void sort(int[] array, int left, int right) {
        if (left == right) return;
        int middle = (left + right) / 2;
        sort(array, left, middle);
        sort(array, middle + 1, right);
        merge(array, left, middle, right);
    }

    private static void merge(int[] array, int left, int middle, int right) {
        int[] temp = new int[right - left + 1];
        int i = left;
        int j = middle + 1;
        int index = 0;
        while (i <= middle && j <= right) {
            if (array[i] > array[j]) {
                temp[index++] = array[j++];
            } else {
                temp[index++] = array[i++];
            }
        }
        while (i <= middle) {
            temp[index++] = array[i++];
        }
        while (j <= right) {
            temp[index++] = array[j++];
        }

        for (int m = 0; m < temp.length; m++) {
            array[m + left] = temp[m];
        }
    }
```




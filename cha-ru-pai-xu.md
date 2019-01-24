时间复杂度：最好情形O\(n\)，平均情形O\(n^2\)，最差情形O\(n^2\)

空间复杂度：O\(1\)

稳定性：不稳定

基本思想：

```
    public static void sort(int[] array) {
        if (array.length == 0) return;
        for (int i = 1; i < array.length; i++) {
            int temp = array[i];
            int j;
            for (j = i - 1; j > -1; j--) {
                if (array[j] > array[j + 1]) {
                    array[j] = array[j] + array[j + 1];
                    array[j + 1] = array[j] - array[j + 1];
                    array[j] = array[j] - array[j + 1];
                } else {
                    break;
                }
            }
        }
    }


    public static void sort2(int[] array) {
        if (array.length == 0) return;
        for (int i = 1; i < array.length; i++) {
            int temp = array[i];
            int j;
            for (j = i - 1; j > -1; j--) {
                if (array[j] > temp) {
                    array[j + 1] = array[j];
                } else {
                    break;
                }
            }
            array[j + 1] = temp;
        }
    }

```




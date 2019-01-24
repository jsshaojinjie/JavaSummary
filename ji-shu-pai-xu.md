时间复杂度：O\(d\(r+n\)\)

空间复杂度：O\(rd+n\)

稳定性：稳定

基本思想：

```
    public static void sort(int[] array) {
        int maxLenght = 0;
        for (int i : array) {
            if (String.valueOf(i).length() > maxLenght) {
                maxLenght = String.valueOf(i).length();
            }
        }
        for (int i = 0; i < maxLenght; i++) {
            int[][] temp = new int[10][array.length];
            int[] secondIndexArray = new int[10];
            for (int j = 0; j < array.length; j++) {
                int index = (int) ((array[j] % (Math.pow(10, i + 1))) / Math.pow(10, i));
                temp[index][secondIndexArray[index]] = array[j];
                secondIndexArray[index] = secondIndexArray[index] + 1;
            }
            int index = 0;
            for (int m = 0; m < 10; m++) {
                for (int n = 0; n < secondIndexArray[m]; n++) {
                    array[index++] = temp[m][n];
                }
            }
        }
    }
```




# Convert 1D Array Into 2D Array


### Java Code

```java

class Solution {
    public int[][] construct2DArray(int[] original, int m, int n) {
        if (original.length != m * n) {
            return new int[0][0]; // Return an empty 2D array if impossible
        }
        
        int[][] result = new int[m][n];
        
        for (int i = 0; i < original.length; i++) {
            result[i / n][i % n] = original[i];
        }
        
        return result;
    }
}
```

![image](https://github.com/user-attachments/assets/cdbb7522-4711-4083-b250-0941c3036da2)

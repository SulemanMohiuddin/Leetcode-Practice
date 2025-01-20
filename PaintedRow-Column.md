# 2661. First Completely Painted Row or Column


## First Try

### Java Code

```java
class Solution {
    public int firstCompleteIndex(int[] arr, int[][] mat) {

        int rows = mat.length;
        int cols = mat[0].length;
        int point = arr.length;
        int flag = 0;

        // We'll use two loops as you requested
        // Create two arrays to track the number of 0s in each row and column
        int[] rowZeroCount = new int[rows];
        int[] colZeroCount = new int[cols];

        
        for (int i = 0; i < point; i++) {
            int num = arr[i];

            
            for (int r = 0; r < rows; r++) {
                for (int c = 0; c < cols; c++) {
                    if (mat[r][c] == num) {
                        mat[r][c] = 0;  

                        
                        rowZeroCount[r]++;
                        colZeroCount[c]++;

                        
                        if (rowZeroCount[r] == cols || colZeroCount[c] == rows) {
                            return i; 
                        }
                    }
                }
            }
        }

        return -1;  
    }
}


```
## final attempt

### Java Code

```java

import java.util.HashMap;
import java.util.Map;

class Solution {
    public int firstCompleteIndex(int[] arr, int[][] mat) {
        int rows = mat.length;
        int cols = mat[0].length;
        int point = arr.length;

        Map<Integer, int[]> numPosition = new HashMap<>();
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                numPosition.put(mat[i][j], new int[]{i, j});
            }
        }

        int[] rowZeroCount = new int[rows];
        int[] colZeroCount = new int[cols];

        for (int i = 0; i < point; i++) {
            int num = arr[i];
            int[] pos = numPosition.get(num);
            if (pos == null) continue;  

            int r = pos[0];
            int c = pos[1];

            mat[r][c] = 0;

            rowZeroCount[r]++;
            colZeroCount[c]++;

            if (rowZeroCount[r] == cols || colZeroCount[c] == rows) {
                return i;
            }
        }

        return -1;  
    }
}


```
![image](https://github.com/user-attachments/assets/2314dd9e-4e56-40b0-a985-b51b348cf8e2)


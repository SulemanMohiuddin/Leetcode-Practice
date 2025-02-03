# Longest Strictly Increasing or Strictly Decreasing Subarray


### Java Code

```java

class Solution {
    public int longestMonotonicSubarray(int[] nums) {
if (nums.length == 0) return 0;

        int maxInc = 1, maxDec = 1;
        int inc = 1, dec = 1;

        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > nums[i - 1]) {
                inc++;
                dec = 1; 
            } else if (nums[i] < nums[i - 1]) {
                dec++;
                inc = 1; 
            } else {
                inc = 1;
                dec = 1;
            }

            maxInc = Math.max(maxInc, inc);
            maxDec = Math.max(maxDec, dec);
        }

        return Math.max(maxInc, maxDec);
    }
}

```

![image](https://github.com/user-attachments/assets/32078ea2-5868-43e6-9e5f-f3a41011230b)

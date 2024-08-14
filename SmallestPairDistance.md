#  Find K-th Smallest Pair Distance


### Java Code

```java

import java.util.Arrays;

class Solution {
    public int smallestDistancePair(int[] nums, int k) {
        Arrays.sort(nums);
        int size = nums.length;
        int left = 0;
        int right = nums[size - 1] - nums[0];

        while (left < right) {
            int mid = left + (right - left) / 2;
            int count = 0;
            int j = 0;

            for (int i = 0; i < size; i++) {
                while (j < size && nums[j] - nums[i] <= mid) {
                    j++;
                }
                count += j - i - 1;
            }

            if (count >= k) {
                right = mid;
            } else {
                left = mid + 1;
            }
        }

        return left;
    }
}


```

![image](https://github.com/user-attachments/assets/c91f6d58-8b16-4677-a3ef-0fb36accaf92)

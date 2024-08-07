# Range Sum of Sorted Subarray Sums


### Java Code

```java


class Solution {
    public int rangeSum(int[] nums, int n, int left, int right) {
        // Calculate the number of subarrays
        int size = nums.length;
        int nsize = (size * (size + 1)) / 2;
        int[] arr = new int[nsize];
        int flag = 0;
        int MOD = 1000000007;  // For large numbers

        // Calculate all subarray sums
        for (int i = 0; i < size; i++) {
            int currentSum = 0;
            for (int j = i; j < size; j++) {
                currentSum += nums[j];
                arr[flag] = currentSum;
                flag++;
            }
        }

        // Sort the array of subarray sums
        Arrays.sort(arr);

        // Calculate the sum from 'left' to 'right' (1-based indices)
        int result = 0;
        for (int i = left - 1; i < right; i++) {
            result = (result + arr[i]) % MOD;
        }

        return result;
    }
}

```

![image](https://github.com/user-attachments/assets/360eb71f-a2c9-43ab-adaf-cd887034d86a)

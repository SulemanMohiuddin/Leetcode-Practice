# Squares of a Sorted Array
Simple question<br>
Simple solution<br>
using only 1 loop

### Java Code

```java



class Solution {
    public int[] sortedSquares(int[] nums) {
        int length = nums.length;

        // Square each element in the array
        for (int i = 0; i < length; i++) {
            nums[i] = nums[i] * nums[i];
        }

        Arrays.sort(nums);

        return nums;
    }
}

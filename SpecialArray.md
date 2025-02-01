# Special Array I


### Java Code

```java
class Solution {
    public boolean isArraySpecial(int[] nums) {
        for (int i = 0; i < nums.length - 1; i++) {
            if ((nums[i] % 2) == (nums[i + 1] % 2)) {
                return false;
            }
        }
        return true;

    }
}
```

![image](https://github.com/user-attachments/assets/b6f15e69-71c1-4a5b-8ba8-f333ffea654f)


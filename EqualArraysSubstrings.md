# Make Two Arrays Equal by Reversing Subarrays


### Java Code

```java

class Solution {
    public boolean canBeEqual(int[] target, int[] arr) {
        Arrays.sort(arr);
        Arrays.sort(target);

        for(int i=0;i<arr.length;i++){
            if(arr[i] != target[i]){
                return false;
            }

        }
        return true;

        
    }
}
```

![image](https://github.com/user-attachments/assets/46f8961e-112f-45ee-be43-346cf409376c)

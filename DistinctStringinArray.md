# Kth Distinct String in an Array
this code is for my first<br>
just testing to see if this works or not


### Java Code

```java

import java.util.ArrayList;

class Solution {
    public String kthDistinct(String[] arr, int k) {
        int size = arr.length;
        ArrayList<String> distinct = new ArrayList<String>(); 

        for (int i = 0; i < size; i++) {
            boolean isDistinct = true; 

            for (int j = 0; j < size; j++) {
                if (i != j && arr[i].equals(arr[j])) { 
                    isDistinct = false;
                    break;
                }
            }

            if (isDistinct) {
                distinct.add(arr[i]);
            }
        }

        if (distinct.size() < k) {
            return ""; 
        } else {
            return distinct.get(k - 1); 
        }
    }
}

```

![image](https://github.com/user-attachments/assets/7faaf5cf-fafc-46e9-93d8-91fc94eb7b39)

<br>
<h3>Using Hash Maps</h3>

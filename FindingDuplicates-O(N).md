# Finding duplicates in array O(N)
this code is for my first<br>
just testing to see if this works or not


### Java Code

```java
class Solution {
    public List<Integer> findDuplicates(int[] nums) {
        Map<Integer, Integer> countMap = new HashMap<>();
        
        for (int num : nums) {
            countMap.put(num, countMap.getOrDefault(num, 0) + 1);
        }
        
        List<Integer> duplicates = new ArrayList<>();
        
        for (Map.Entry<Integer, Integer> entry : countMap.entrySet()) {
            if (entry.getValue() > 1) {
                duplicates.add(entry.getKey());
            }
        }
         int[] duplicatesArray = duplicates.stream().mapToInt(Integer::intValue).toArray();
        
        return duplicates;
    }
}
```
not my proudest moment

![image](https://github.com/user-attachments/assets/8b08917e-af8f-4b8b-8d27-6bcaf65c6dd0)

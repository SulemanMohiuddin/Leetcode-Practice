# Combination Sum II


### Java Code

```java

class Solution {
 public List<List<Integer>> combinationSum2(int[] candidates, int target) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(candidates);  // Sort to handle duplicates easily
        backtrack(result, new ArrayList<>(), candidates, target, 0);
        return result;
    }

    private void backtrack(List<List<Integer>> result, List<Integer> tempList, int[] candidates, int target, int start) {
        if (target == 0) {
            result.add(new ArrayList<>(tempList));
            return;
        }
        if (target < 0) {
            return;
        }
        
        for (int i = start; i < candidates.length; i++) {
            if (i > start && candidates[i] == candidates[i - 1]) {
                continue;  // Skip duplicates
            }
            tempList.add(candidates[i]);
            backtrack(result, tempList, candidates, target - candidates[i], i + 1);
            tempList.remove(tempList.size() - 1);  // Backtrack
        }
    }


}

```

![image](https://github.com/user-attachments/assets/e095a4ea-5ee7-4125-b383-f07c5cd90857)


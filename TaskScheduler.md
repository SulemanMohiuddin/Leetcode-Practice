# Task Scheduler


### Java Code

```java

class Solution {
    public int leastInterval(char[] tasks, int n) {
        int[] taskCounts = new int[26];
        
        // Count the frequency of each task
        for (char task : tasks) {
            taskCounts[task - 'A']++;
        }
        
        Arrays.sort(taskCounts);
        int maxFreq = taskCounts[25];
        
        int idleSlots = (maxFreq - 1) * n;
        
        // Fill the idle slots with remaining tasks
        for (int i = 24; i >= 0 && idleSlots > 0; i--) {
            idleSlots -= Math.min(taskCounts[i], maxFreq - 1);
        }
        
        // If idleSlots is positive, it means we have some idle time
        idleSlots = Math.max(0, idleSlots);
        
        return tasks.length + idleSlots;
    }
}

```
![image](https://github.com/user-attachments/assets/652ae8fd-3f83-41f2-973d-7e7593454a19)





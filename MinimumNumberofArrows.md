# Minimum Number of Arrows to Burst Balloons
-I`m quite proud of this one as I thought of the whole algorithm before and coded it<br>
-My thought process was as stated ;<br>
&emsp;&emsp;&emsp; 1 - Firstly i placed all the balloons on a grid and then looked for any thing that might help me<br>
&emsp;&emsp;&emsp; 2 - I quickly found out that the end of the balloon must be greater then other balloons to take 1 arrow<br>
&emsp;&emsp;&emsp; 3 - But there was a problem what if the other balloon is way at the end and i already move on to another balloon?<br>
&emsp;&emsp;&emsp; 4 - I asked gpt if we can arrange the balloons in ascending order fixing the issue and lo and behold we can<br>
&emsp;&emsp;&emsp; 5 - then i wrote an algorithm and coded it

![image](https://github.com/user-attachments/assets/4761388f-d730-473b-9ee4-028b19e4ffec)



### Java Code

```java
class Solution {
    public int findMinArrowShots(int[][] points) {
                if (points == null || points.length == 0) {
            return 0;
        }

        // Sort balloons based on their end positions (xend)
        //got this from gpt hey im still learning
        Arrays.sort(points, Comparator.comparingInt(a -> a[1]));

        // Initialize arrow count and position of the first arrow
        int arrows = 1; 
        int currentEnd = points[0][1]; // End position of the first balloon

        for (int i = 1; i < points.length; i++) {
            // If the start of the current balloon is greater than the current end
            //this will only happen when the ballons stop to overlap as they are sorted
            if (points[i][0] > currentEnd) {
                // Shoot a new arrow
                arrows++;
                currentEnd = points[i][1]; // Update current end to the end of the new balloon
            }
        }
        return arrows;
    }
}
```
![image](https://github.com/user-attachments/assets/15b6103a-833d-4102-93aa-5e9c5396c2de)


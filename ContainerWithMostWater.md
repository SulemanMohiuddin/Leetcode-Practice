# Container With Most Water
-used the pointer method to traverse and only used 1 loop still got 5 ms thats was the slowest solution

<img src="https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg">

### Java Code

```java


class Solution {
    public int maxArea(int[] height) {
        int max=0;
        int size=height.length;
        int area=0;
        int left=0;
        int right=size-1;
        while(left<=right){
            int dist=right-left;

            int currentHeight = Math.min(height[left], height[right]);
            int currentArea = currentHeight * dist;
            area = Math.max(area, currentArea);

            if (height[left]<height[right]){
                left++;
            }
            else{
                right--;
            }
        }
        return area;
    }
}

# merge 2 arrays and find the median (time coplexity Log(m+n))

my solution has the complexity of (m+n)Log(m+n)


### Java Code

```java

class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        
        //initialzie array
        int[] mergedArray = new int[nums1.length + nums2.length];

        //mergeing the arrays
        System.arraycopy(nums1, 0, mergedArray, 0, nums1.length);
        System.arraycopy(nums2, 0, mergedArray, nums1.length, nums2.length);

        // Sort the combined array
        Arrays.sort(mergedArray);

        // Calculate the median
        int n = mergedArray.length;
        if (n % 2 == 0) {
            // If the total number of elements is even
            return (mergedArray[n / 2 - 1] + mergedArray[n / 2]) / 2.0;
        } else {
            // If the total number of elements is odd
            return mergedArray[n / 2];
        }

        
    }
}

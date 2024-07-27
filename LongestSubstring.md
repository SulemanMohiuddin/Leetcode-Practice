# Longest Substring Without Repeating Characters

used hashmap to map each character of the string and then compared them until a match was found and then took the distance btw them

### Java Code

```java 

class Solution {
    public int lengthOfLongestSubstring(String s) {
        int max = 0;
        int left = 0;
        
        Set<Character> seen = new HashSet<>();

        for (int right = 0; right < s.length(); right++) {

            // Remove characters until the duplicate character is removed
            while (seen.contains(s.charAt(right))) {
                seen.remove(s.charAt(left));
                left++;
            }

            // Add the current character to the set
            seen.add(s.charAt(right));
            
            // Update the maximum length
            max = Math.max(max, right - left + 1);
        }
        
        return max;
    }
}

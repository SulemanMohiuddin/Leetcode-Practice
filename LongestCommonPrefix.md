# Longest Common Prefix

 

### Java Code

```java

class Solution {
    public String longestCommonPrefix(String[] strs) {
        if (strs == null || strs.length == 0) {
            return "";
        }

        String prefix = strs[0]; // Start with the first string as the initial prefix

        // Check each string in the array against the current prefix
        for (int i = 1; i < strs.length; i++) {
            while (strs[i].indexOf(prefix) != 0) {
                // If current prefix is not a prefix of strs[i], reduce it
                prefix = prefix.substring(0, prefix.length() - 1);
                // If prefix becomes empty, return ""
                if (prefix.isEmpty()) {
                    return "";
                }
            }
        }

        return prefix;
    }
}
```

![image](https://github.com/user-attachments/assets/6911024d-f937-4aa6-8e4c-f973d1d23b4f)
